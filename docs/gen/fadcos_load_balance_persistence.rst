:source: fadcos_load_balance_persistence.py

:orphan:

.. fadcos_load_balance_persistence:

fadcos_load_balance_persistence -- configure load balance persistence in Fortinet's FortiADC
++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++

.. versionadded:: 1.1.0

.. contents::
   :local:
   :depth: 1


Synopsis
--------
- Configure load balance persistence of Application Resources in Server Load Balance Page 



Requirements
------------
The below requirements are needed on the host that executes this module.

- ansible>=2.8


FortiADC Version Compatibility
------------------------------


.. raw:: html

 <br>
 <table>
 <tr>
 <td></td>
 <td><code class="docutils literal notranslate">v7.1.4 </code></td>
 <td><code class="docutils literal notranslate">v7.2.2 </code></td>
 <td><code class="docutils literal notranslate">v7.4.0 </code></td>
 </tr>
 <tr>
 <td>fadcos_load_balance_persistence</td>
 <td>yes</td>
 <td>yes</td>
 <td>yes</td>
 </tr>
 </table>
 <p>



Parameters
----------


.. raw:: html

    <ul>
    <li> <span class="li-head">action</span> - Type of action to perform on the object. <span class="li-normal">type: str</span> <span class="li-required">required: true</span> </li>
    <li> <span class="li-head">name</span> - config load-balance persistence name <span class="li-normal">type: str</span> <span class="li-required">required: false</span> </li>
    <li> <span class="li-head">type</span> - Specify the Radius attribute type.<span class="li-normal">type: str</span> <span class="li-required">required: false</span> </li>
    <li> <span class="li-head">timeout</span> - Specify the timeout (in seconds) for an inactive persistence session table entry. (Range: 1-86400).<span class="li-normal">type: int</span> <span class="li-required">required: false</span> <span class="li-normal">default: 300</span> </li>
    <li> <span class="li-head">ipv4_maskbits</span> - Specify the number of bits in a IPv4 subnet mask to specify a network segment that should follow the persistence rule. (Range: 1-32).<span class="li-normal">type: str</span> <span class="li-required">required: false</span> <span class="li-normal">default: 32</span> </li>
    <li> <span class="li-head">ipv6_maskbits</span> - Specify the number of bits in a IPv6 subnet mask to specify a network segment that should follow the persistence rule. (Range: 1-128).<span class="li-normal">type: str</span> <span class="li-required">required: false</span> <span class="li-normal">default: 128</span> </li>
    <li> <span class="li-head">match_across_virtual_servers</span> - If enabled, clients will continue to access the same backend server through different virtual servers for the duration of a session.<span class="li-normal">type: str</span> <span class="li-required">required: false</span> <span class="li-normal">default: disable</span> </li>
    <li> <span class="li-head">keyword</span> - Specify the HTTP header value, URL paramter or cookie name which is depended on the radius attribute type.<span class="li-normal">type: str</span> <span class="li-required">required: false</span> </li>
    <li> <span class="li-head">sess_kw_type</span> - Specify the cookie which is generated from the server.<span class="li-normal">type: str</span> <span class="li-required">required: false</span> <span class="li-normal">default: auto</span> </li>
    <li> <span class="li-head">cookie_domain</span> - Specifies the domain attribute of the cookie.<span class="li-normal">type: str</span> <span class="li-required">required: false</span> <span class="li-normal">default: </span> </li>
    <li> <span class="li-head">cookie_httponly</span> - Enable/disable to add the "HTTPOnly" flag to cookies.<span class="li-normal">type: str</span> <span class="li-required">required: false</span> <span class="li-normal">default: disable</span> </li>
    <li> <span class="li-head">cookie_secure</span> - Enable/disable to add the Secure flag to cookies.<span class="li-normal">type: str</span> <span class="li-required">required: false</span> <span class="li-normal">default: disable</span> </li>
    <li> <span class="li-head">cookie_samesite</span> - Add a SameSite attribute to prevent the browser from sending cookies along with cross-site requests, to mitigate the risk of cross-origin information leakage.<span class="li-normal">type: str</span> <span class="li-required">required: false</span> <span class="li-normal">default: nothing</span> </li>
    <li> <span class="li-head">cookie_custom_attr</span> - Enable/disable to specify custom attributes.<span class="li-normal">type: str</span> <span class="li-required">required: false</span> <span class="li-normal">default: disable</span> </li>
    <li> <span class="li-head">cookie_custom_attr_val</span> - The cookie-custom-attr-value option appears if cookie-custom-attr is enabled.<span class="li-normal">type: str</span> <span class="li-required">required: false</span> </li>
    <li> <span class="li-head">match_across_servers</span> - An option for radius-attribute and source-address persistence methods.<span class="li-normal">type: str</span> <span class="li-required">required: false</span> <span class="li-normal">default: disable</span> </li>
    <li> <span class="li-head">override_connection_limit</span> - An option for radius-attribute only.<span class="li-normal">type: str</span> <span class="li-required">required: false</span> <span class="li-normal">default: disable</span> </li>
    <li> <span class="li-head">radius_attribute_relation</span> - Specify the relation when multiple radius attributes are configured.<span class="li-normal">type: str</span> <span class="li-required">required: false</span> <span class="li-normal">default: AND</span> </li>
    <li> <span class="li-head">iso8583_bitmap_relation</span> - Specify the relation among the bitmap type be AND/OR.<span class="li-normal">type: str</span> <span class="li-required">required: false</span> <span class="li-normal">default: OR</span> </li>
    <li> <span class="li-head">keyvalue_relation</span> - Specify the relation of keyvalue be AND/OR if iso8583_bitmap_relation is OR.<span class="li-normal">type: str</span> <span class="li-required">required: false</span> <span class="li-normal">default: AND</span> </li>
    <li> <span class="li-head">names</span> - load-balance persistence name list<span class="li-normal">type: list</span> <span class="li-required">required: false</span></li>
    <li> <span class="li-head">vdom</span> - VDOM name if enabled.<span class="li-normal">type: str</span> <span class="li-required">required: true(if VDOM is enabled)</span></li>
    </ul>


Examples
--------

.. code-block:: yaml+jinja

        - name:
          hosts: all
          vars:
          connection: httpapi
          gather_facts: false
          tasks:
            - name: create
              fadcos_load_balance_persistence:
               action: add
               name: test1
               type: source-address
               timeout: 300
               ipv4_maskbits: '32'
               ipv6_maskbits: '128'
               match_across_virtual_servers: disable

            - name: create
              fadcos_load_balance_persistence:
               action: add
               name: test2
               type: consistent-hash-ip

            - name: create
              fadcos_load_balance_persistence:
               action: add
               name: test3
               type: hash-source-address-port

            - name: create
              fadcos_load_balance_persistence:
               action: add
               name: test4
               type: hash-http-header
               keyword: keyword

            - name: create
              fadcos_load_balance_persistence:
               action: add
               name: test5
               type: hash-http-request
               keyword: keyword

            - name: create
              fadcos_load_balance_persistence:
               action: add
               name: test6
               type: hash-cookie
               keyword: keyword

            - name: create
              fadcos_load_balance_persistence:
               action: add
               name: test7
               type: persistent-cookie
               keyword: keyword
               timeout: 300

            - name: create
              fadcos_load_balance_persistence:
               action: add
               name: test8
               type: passive-cookie
               keyword: keyword
               timeout: 300
               sess_kw_type: auto

            - name: create
              fadcos_load_balance_persistence:
               action: add
               name: test9
               type: insert-cookie
               keyword: keyword
               timeout: 300
               cookie_domain: ""
               cookie_httponly: disable
               cookie_secure: disable
               cookie_samesite: nothing
               cookie_custom_attr: disable

            - name: create
              fadcos_load_balance_persistence:
               action: add
               name: test10
               type: rewrite-cookie
               keyword: keyword

            - name: create
              fadcos_load_balance_persistence:
               action: add
               name: test11
               type: embedded-cookie
               keyword: keyword

            - name: create
              fadcos_load_balance_persistence:
               action: add
               name: test12
               type: radius-attribute
               timeout: 400
               match_across_servers: enable
               override_connection_limit: enable
               radius_attribute_relation: OR

            - name: create
              fadcos_load_balance_persistence:
               action: add
               name: test13
               type: ssl-session-id
               timeout: 400

            - name: create
              fadcos_load_balance_persistence:
               action: add
               name: test14
               type: sip-call-id
               timeout: 400

            - name: create
              fadcos_load_balance_persistence:
               action: add
               name: test15
               type: rdp-cookie

            - name: create
              fadcos_load_balance_persistence:
               action: add
               name: test16
               type: iso8583-bitmap
               timeout: 400
               iso8583_bitmap_relation: OR
               keyvalue_relation: AND

            - name: get
              fadcos_load_balance_persistence:
               action: get

            - name: delete
              fadcos_load_balance_persistence:
               action: remove
               names:
                    - test1

    
Return Values
-------------
Common return values are documented: https://docs.ansible.com/ansible/latest/reference_appendices/common_return_values.html#common-return-values, the following are the fields unique to this module:

.. raw:: html

    <ul>

    <li> <span class="li-return">200</span> - OK: Request returns successful. </li>
    <li> <span class="li-return">400</span> - Bad Request: Request cannot be processed by the API. </li>
    <li> <span class="li-return">401</span> - Not Authorized: Request without successful login session. </li>
    <li> <span class="li-return">403</span> - Forbidden: Request is missing CSRF token or administrator is missing access profile permissions. </li>
    <li> <span class="li-return">404</span> - Resource Not Found: Unable to find the specified resource. </li>
    <li> <span class="li-return">405</span> - Method Not Allowed: Specified HTTP method is not allowed for this resource. </li>
    <li> <span class="li-return">413</span> - Request Entity Too Large: Request cannot be processed due to large entity.</li>
    <li> <span class="li-return">424</span> - Failed Dependency: Fail dependency can be duplicate resource, missing required parameter, missing required attribute, or invalid attribute value.</li>
    <li> <span class="li-return">429</span> -  Access temporarily blocked: Maximum failed authentications reached. The offended source is temporarily blocked for certain amount of time.</li>
    <li> <span class="li-return">500</span> -  Internal Server Error: Internal error when processing the request.</li>
    </ul>

For errorcode please check FortiADC API errorcode at : https://fndn.fortinet.net/index.php?/fortiapi/981-fortiadc/

Status
------

- This module is not guaranteed to have a backwards compatible interface.


Authors
-------

- Wayne Chou


.. hint::
    If you notice any issues in this documentation, you can create a pull request to improve it.
