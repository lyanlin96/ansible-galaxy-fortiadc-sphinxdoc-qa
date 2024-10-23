:source: fadcos_waf_allowed_origin_list.py

:orphan:

.. fadcos_waf_allowed_origin_list:

fadcos_waf_allowed_origin_list -- Configuring a list entry of a Allowed Origin List
++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++

.. versionadded:: 1.3.0

.. contents::
   :local:
   :depth: 1


Synopsis
--------
- Configuring a list entry of a Allowed Origin List



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
 <td>fadcos_waf_allowed_origin_list</td>
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
    <li> <span class="li-head">name</span> - Specify the name of the <span class="li-normal">type: str</span> <span class="li-required">required: true</span> </li>
    <li> <span class="li-head">origin_name</span> - The foreign application's domain name or IP address.<span class="li-normal">type: str</span> <span class="li-required">required: false</span></li>
    <li> <span class="li-head">port</span> - Specify the TCP port number for the CORS connections. (Range: 0-65535; default: 80).<span class="li-normal">type: str</span> <span class="li-required">required: false</span> <span class="li-normal">default: 80</span> </li>
    <li> <span class="li-head">protocol</span> - Select which type of protocols are allowed for the connections between foreign applications and your application.<span class="li-normal">type: str</span> <span class="li-required">required: false</span></li>
    <li> <span class="li-head">include_sub_domains</span> - Enable/disable to allow/disallow the Origin Value to match with the domains of its sub level.<span class="li-normal">type: str</span> <span class="li-required">required: false</span></li>
    <li> <span class="li-head">vdom</span> - VDOM name if enabled.<span class="li-normal">type: str</span> <span class="li-required">required: true(if VDOM is enabled)</li>
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
            - name: Add WAF allowed_origin_child_allowed_origin_list entry
              fadcos_waf_allowed_origin_list:
                action: add
                name: awo
                origin_name: new_org
                port: 8080  
                protocol: HTTP
                include_sub_domains: disable

            - name: edit WAF allowed_origin_child_allowed_origin_list entry
              fadcos_waf_allowed_origin_list:
                action: edit
                name: awo
                id: 1
                origin_name: new_org1
                port: 80  
                protocol: HTTPS
                include_sub_domains: enable

            - name: delete WAF allowed_origin_child_allowed_origin_list entry
              fadcos_waf_allowed_origin_list:
                action: delete
                name: awo
                id: 1 
            
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

- Joseph Chen


.. hint::
    If you notice any issues in this documentation, you can create a pull request to improve it.
