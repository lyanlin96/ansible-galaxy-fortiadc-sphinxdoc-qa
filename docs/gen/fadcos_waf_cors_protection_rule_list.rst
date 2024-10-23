:source: fadcos_waf_cors_protection_rule_list.py

:orphan:

.. fadcos_waf_cors_protection_rule_list:

fadcos_waf_cors_protection_rule_list -- Configuring a Rule object of a CORS Protection Policy 
++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++

.. versionadded:: 1.3.0

.. contents::
   :local:
   :depth: 1


Synopsis
--------
- Configuring a Rule object of a CORS Protection Policy 



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
 <td>fadcos_waf_cors_protection_rule_list</td>
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
    <li> <span class="li-head">name</span> - Specify the name of the rule. <span class="li-normal">type: str</span> <span class="li-required">required: true</span> </li>
    <li> <span class="li-head">host_status</span> - Enable/disable to allow this rule to protect a specific domain name or IP address. <span class="li-normal">type: str</span> <span class="li-required">required: false</span> </li>
    <li> <span class="li-head">host</span> - Specify the host name. <span class="li-normal">type: str</span> <span class="li-required">required: false</span> </li>
    <li> <span class="li-head">id</span> - Specify the ID of rule in the protection rule list.<span class="li-normal">type: int</span> <span class="li-required">required: false</span> </li>
    <li> <span class="li-head">allowed_headers</span> - Enable/disable to allow FortiADC to use the CORS Headers List to verify whether the headers used in the CORS requests are legitimate.  <span class="li-normal">type: str</span> <span class="li-required">required: false</span> </li>
    <li> <span class="li-head">allowed_headers_list</span> - Specify the name of the CORS Headers List to allow. <span class="li-normal">type: str</span> <span class="li-required">required: false</span> </li>
    <li> <span class="li-head">allowed_methods</span> - Enable/disable to allow FortiADC to use the Methods specified to verify whether the methods used in the CORS requests are legitimate. <span class="li-normal">type: str</span> <span class="li-required">required: false</span> </li>
    <li> <span class="li-head">allowed_origin</span> - Specify the name of the Allowed Origin. <span class="li-normal">type: str</span> <span class="li-required">required: false</span> </li>
    <li> <span class="li-head">apply_to_all_cors_traffic</span> - Enable/disable to apply the CORS Protection Rule to all CORS traffic. <span class="li-normal">type: str</span> <span class="li-required">required: false</span> </li>
    <li> <span class="li-head">exposed_headers</span> - Enable/disable to allow FortiADC to expose the specified headers in the CORS Headers List in JavaScript and share with foreign applications. <span class="li-normal">type: str</span> <span class="li-required">required: false</span> </li>
    <li> <span class="li-head">exposed_headers_list</span> - Specify the name of the CORS Headers List to expose. <span class="li-normal">type: str</span> <span class="li-required">required: false</span> </li>
    <li> <span class="li-head">insert_allowed_credentials</span> - Enable/disable to allow whether the CORS requests from foreign applications can include user credentials.  <span class="li-normal">type: str</span> <span class="li-required">required: false</span> </li>
    <li> <span class="li-head">allowed_credentials</span> - Specify the allow Credentials to be inserted. <span class="li-normal">type: str</span> <span class="li-required">required: false</span> </li>
    <li> <span class="li-head">insert_max_age</span> - Enable/disable to specify a maximum time period before the result of the preflight request expires. <span class="li-normal">type: str</span> <span class="li-required">required: false</span> </li>
    <li> <span class="li-head">allowed_max_age</span> - Specify the maximum time period in seconds.  <span class="li-normal">type: str</span> <span class="li-required">required: false</span> </li>
    <li> <span class="li-head">methods</span> - Specify the methods. <span class="li-normal">type: str</span> <span class="li-required">required: false</span> </li>
    <li> <span class="li-head">request_url</span> - Specify the request URL as a regular expression. <span class="li-normal">type: str</span> <span class="li-required">required: false</span> </li>
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
            - name: Add WAF cors_protection_rule_list entry
              fadcos_waf_cors_protection_rule_list:
                action: add
                name: test_cp
                allowed_credentials: false
                allowed_headers: enable
                allowed_headers_list: cor1
                allowed_max_age: 0
                allowed_methods: enable
                allowed_origin: awo
                apply_to_all_cors_traffic: disable
                exposed_headers: enable
                exposed_headers_list: cor1
                host: jjjjj
                host_status: enable
                insert_allowed_credentials: enable
                insert_max_age: enable
                methods: GET HEAD TRACE CONNECT
                request_url: /test/jjjjj

            - name: edit WAF cors_protection_rule_list entry
              fadcos_waf_cors_protection_rule_list:
                action: edit
                name: test_cp
                id: 3
                allowed_credentials: false
                host: zzzz
                request_url: /test/zzzzz

            - name: get WAF cors_protection_rule_list entry
              fadcos_waf_cors_protection_rule_list:
                action: get
                name: test_cp
                id: 3

            - name: delete WAF cors_protection_rule_list entry
              fadcos_waf_cors_protection_rule_list:
                action: delete
                name: test_cp
                id: 1

            - name: delete WAF cors_protection_rule_list entry
              fadcos_waf_cors_protection_rule_list:
                action: delete
                name: test_cp
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
