:source: fadcos_waf_profile.py

:orphan:

.. fadcos_waf_profile:

fadcos_waf_profile -- Configuring a WAF Profile
++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++

.. versionadded:: 1.3.0

.. contents::
   :local:
   :depth: 1


Synopsis
--------
- Configuring a WAF Profile



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
 <td>fadcos_waf_profile</td>
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
    <li> <span class="li-head">name</span> - Configuration name. Valid characters are A-Z, a-z, 0-9, _, and -. No spaces. <span class="li-normal">type: str</span> <span class="li-required">required: true</span> </li>
    <li> <span class="li-head">exception_name</span> - Select a user-defined exception configuration object. Exceptions identify specific hosts or URL patterns that are not subject to processing by this rule.<span class="li-normal">type: str</span> <span class="li-required">required: false</span> </li>
    <li> <span class="li-head">desc</span> - A string to describe the purpose of the configuration, to help you and other administrators more easily identify its use.<span class="li-normal">type: int</span> <span class="li-required">required: false</span> </li>
    <li> <span class="li-head">rule_match_record</span> - Enable to allow the Security Log to display the part of the rule that is matched when the security event is logged. This is disabled by default. <span class="li-normal">type: str</span> <span class="li-required">required: false</span></li>
    <li> <span class="li-head">adaptive_learning</span> - Select a predefined or user-defined Adaptive Learning configuration object.<span class="li-normal">type: str</span> <span class="li-required">required: true</span> </li>
    <li> <span class="li-head">web_attack_signature</span> - Select a predefined or user-defined Web Attack Signature configuration object.<span class="li-normal">type: str</span> <span class="li-required">required: false</span> </li>
    <li> <span class="li-head">http_protocol_constraint</span> - Select a predefined or user-defined HTTP Protocol Constraint configuration object.<span class="li-normal">type: int</span> <span class="li-required">required: false</span> </li>
    <li> <span class="li-head">cookie_security</span> - Select a user-defined Cookie Security configuration object. <span class="li-normal">type: str</span> <span class="li-required">required: false</span></li>
    <li> <span class="li-head">data_leak_prevention_name</span> - Select a user-defined Data Leak Prevention configuration object.<span class="li-normal">type: str</span> <span class="li-required">required: true</span> </li>
    <li> <span class="li-head">http_header_security_name</span> - Select a user-defined HTTP Header Security configuration object.<span class="li-normal">type: str</span> <span class="li-required">required: false</span> </li>
    <li> <span class="li-head">heuristic_sql_xss_injection_detection</span> - Select a predefined or user-defined SQL/XSS Injection Detection configuration object.<span class="li-normal">type: int</span> <span class="li-required">required: false</span> </li>
    <li> <span class="li-head">input_validation_policy_name</span> - Select a user-defined Input Validation Policy configuration object. <span class="li-normal">type: str</span> <span class="li-required">required: false</span></li>
    <li> <span class="li-head">xml_validation_name</span> - Select a predefined or user-defined XML Detection configuration object.<span class="li-normal">type: str</span> <span class="li-required">required: true(if VDOM is enabled)</span></li>
    <li> <span class="li-head">cors_protection</span> - Select a user-defined CORS Protection configuration object.<span class="li-normal">type: str</span> <span class="li-required">required: true(if VDOM is enabled)</span></li>
    <li> <span class="li-head">brute_force_login_name</span> - Select a user-defined Brute Force Attack Detection configuration object.<span class="li-normal">type: str</span> <span class="li-required">required: true(if VDOM is enabled)</span></li>
    <li> <span class="li-head">url_protection</span> - Select a user-defined URL Protection configuration object.<span class="li-normal">type: str</span> <span class="li-required">required: true(if VDOM is enabled)</span></li>
    <li> <span class="li-head">credential_stuffing_defense</span> - Select a user-defined Credential Stuffing Defense configuration object.<span class="li-normal">type: str</span> <span class="li-required">required: true(if VDOM is enabled)</span></li>
    <li> <span class="li-head">json_validation_name</span> - Select a predefined or user-defined JSON Detection configuration object.<span class="li-normal">type: str</span> <span class="li-required">required: true(if VDOM is enabled)</span></li>
    <li> <span class="li-head">openapi_validation_name</span> - Select a user-defined OpenAPI Detection configuration object.<span class="li-normal">type: str</span> <span class="li-required">required: true(if VDOM is enabled)</span></li>
    <li> <span class="li-head">api_gateway_policy_name</span> - Select a user-defined API Gateway configuration object.<span class="li-normal">type: str</span> <span class="li-required">required: true(if VDOM is enabled)</span></li>
    <li> <span class="li-head">bot_detection_name</span> - Select a user-defined Bot Detection configuration object.<span class="li-normal">type: str</span> <span class="li-required">required: true(if VDOM is enabled)</span></li>
    <li> <span class="li-head">threshold_based_detection</span> - Select a predefined or user-defined Threshold Based Detection configuration object.<span class="li-normal">type: str</span> <span class="li-required">required: true(if VDOM is enabled)</span></li>
    <li> <span class="li-head">biometrics_based_detection</span> - Select a user-defined Biometrics Based Detection configuration object.<span class="li-normal">type: str</span> <span class="li-required">required: true(if VDOM is enabled)</span></li>
    <li> <span class="li-head">fingerprint_based_detection</span> - Select a user-defined Fingerprint Based Detection configuration object.<span class="li-normal">type: str</span> <span class="li-required">required: true(if VDOM is enabled)</span></li>
    <li> <span class="li-head">bot_detection_name</span> - Select a user-defined Advanced Bot Protection configuration object.<span class="li-normal">type: str</span> <span class="li-required">required: true(if VDOM is enabled)</span></li>
    <li> <span class="li-head">advanced_protection_name</span> - Select a user-defined Advanced Protection configuration object.<span class="li-normal">type: str</span> <span class="li-required">required: true(if VDOM is enabled)</span></li>
    <li> <span class="li-head">csrf_protection</span> - Select a user-defined CSRF Protection configuration object.<span class="li-normal">type: str</span> <span class="li-required">required: true(if VDOM is enabled)</span></li>
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
            - name: Add WAF Profile
              fadcos_waf_profile:
                action: add
                name: waf_tt1

            - name: Get WAF Profile
              fadcos_waf_profile:
                action: get
                name: waf_tt1

            - name: Edit WAF Profile
              fadcos_waf_profile:
                action: edit
                name: waf_tt1
                adaptive_learning: Medium_Learning
                cookie_security: CE1

            - name: Delete WAF Profile
              fadcos_waf_profile:
                action: delete
                name: waf_tt1
            
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
