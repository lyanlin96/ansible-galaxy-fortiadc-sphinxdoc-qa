:source: fadcos_waf_json_validation_detection.py

:orphan:

.. fadcos_waf_json_validation_detection:

fadcos_waf_json_validation_detection -- Configuring JSON detection
++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++

.. versionadded:: 1.3.0

.. contents::
   :local:
   :depth: 1


Synopsis
--------
- Configuring JSON detection



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
 <td>fadcos_waf_json_validation_detection</td>
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
    <li> <span class="li-head">name</span> - Specify the name of the JSON Detection profile. <span class="li-normal">type: str</span> <span class="li-required">required: true</span> </li>
    <li> <span class="li-head">severity</span> - Set the severity level in WAF logs of potential attacks detected by the JSON Detection profile. <span class="li-normal">type: str</span> <span class="li-required">required: false</span> </li>
    <li> <span class="li-head">security_action</span> - Select the action profile that you want to apply.<span class="li-normal">type: str</span> <span class="li-required">required: false</span> </li>
    <li> <span class="li-head">exception_id</span> - Optional. Select the exception profile that you want to apply to the JSON Detection profile.<span class="li-normal">type: int</span> <span class="li-required">required: false</span> </li>
    <li> <span class="li-head">json_format_checks</span> - Enable to configure security checks for incoming HTTP requests to determine whether they are well-formed. <span class="li-normal">type: str</span> <span class="li-required">required: false</span></li>
    <li> <span class="li-head">json_limit_checks</span> - Enable to enforce parsing limits to protect web servers from attacks such as DOS attacks. If enabled, you may change the configuration for the following parameters (limit_max_array_value, limit_max_depth, limit_max_object_member, limit_max_string). <span class="li-normal">type: str</span> <span class="li-required">required: true</span> </li>
    <li> <span class="li-head">json_schema_checks</span> - Specify the name of the <span class="li-normal">type: str</span> <span class="li-required">required: true</span> </li>
    <li> <span class="li-head">json_sql_injection_checks</span> - Enable to examine the bodies of incoming requests for inappropriate SQL characters and keywords that might indicate an SQL injection attack.<span class="li-normal">type: str</span> <span class="li-required">required: false</span> </li>
    <li> <span class="li-head">json_xss_checks</span> - Enable to examine the bodies of incoming JSON requests that might indicate possible cross-site scripting attacks.<span class="li-normal">type: int</span> <span class="li-required">required: false</span> </li>
    <li> <span class="li-head">limit_max_array_value</span> - Limits the maximum number of values within a single array. The default value is 256. The valid range is 0~4096. Available only when JSON Limit Checks is enabled. <span class="li-normal">type: str</span> <span class="li-required">required: false</span></li>
    <li> <span class="li-head">limit_max_depth</span> - Limits the maximum depth in a JSON value. The default value is 16. The valid range is 0~4096. Available only when JSON Limit Checks is enabled.<span class="li-normal">type: str</span> <span class="li-required">required: false</span> </li>
    <li> <span class="li-head">limit_max_object_member</span> - Limits the number of members in a JSON object. The default value is 64. The valid range is 0~4096. Available only when JSON Limit Checks is enabled.<span class="li-normal">type: int</span> <span class="li-required">required: false</span> </li>
    <li> <span class="li-head">limit_max_string</span> - 	Limits the length of a string in a JSON request for a name or a value. The default value is 64. The valid range is 0~4096. Available only when JSON Limit Checks is enabled. <span class="li-normal">type: str</span> <span class="li-required">required: false</span></li>
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
            - name: Add WAF json_validation_detection
              fadcos_waf_json_validation_detection:
                action: add
                name: jst1
                security_action: alert
                exception_id: n1
                json_format_checks: enable
                json_limit_checks: disable
                json_schema_checks: disable
                json_sql_injection_checks: disable
                json_xss_checks: enable
                limit_max_array_value: 256
                limit_max_depth: 16
                limit_max_object_member: 64
                limit_max_string: 64

            - name: Add WAF duplicate json_validation_detection 
              fadcos_waf_json_validation_detection:
                action: add
                name: jst1
                security_action: alert
                exception_id: n1
                json_format_checks: enable
                json_limit_checks: disable
                json_schema_checks: disable

            - name: edit WAF json_validation_detection
              fadcos_waf_json_validation_detection:
                action: edit
                name: jst1
                security_action: block
                exception_id: n1
                limit_max_array_value: 200
                limit_max_depth: 32
                limit_max_object_member: 48
                severity: high

            - name: get WAF json_validation_detection
              fadcos_waf_json_validation_detection:
                action: get
                name: jst1

            - name: delete WAF json_validation_detection
              fadcos_waf_json_validation_detection:
                action: delete
                name: JS1

            - name: delete non-existant WAF json_validation_detection
              fadcos_waf_json_validation_detection:
                action: delete
                name: JS1
            
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
