:source: fadcos_waf_heuristic_sql_xss_injection_detection.py

:orphan:

.. fadcos_waf_heuristic_sql_xss_injection_detection:

fadcos_waf_heuristic_sql_xss_injection_detection -- Configuring an SQL/XSS Injection Detection policy
++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++

.. versionadded:: 1.3.0

.. contents::
   :local:
   :depth: 1


Synopsis
--------
- Configuring an SQL/XSS Injection Detection policy



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
 <td>fadcos_waf_heuristic_sql_xss_injection_detection</td>
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
    <li> <span class="li-head">body_sql_injection_detection</span> - Switch of the body SQL injection detection (enable or disable).<span class="li-normal">type: str</span> <span class="li-required">required: false</span> </li>
    <li> <span class="li-head">body_xss_detection</span> - Switch of the body XSS detection  (enable or disable).<span class="li-normal">type: int</span> <span class="li-required">required: false</span> </li>
    <li> <span class="li-head">cookie_sql_injection_detection</span> -  Switch of the cookie SQL injection detection (enable or disable). <span class="li-normal">type: str</span> <span class="li-required">required: false</span></li>
    <li> <span class="li-head">cookie_xss_detection</span> -  Switch of the cookie XSS detection (enable or disable). <span class="li-normal">type: str</span> <span class="li-required">required: false</span></li>
    <li> <span class="li-head">refer_sql_injection_detection</span> -  Switch of the Refer SQL injection detection (enable or disable). <span class="li-normal">type: str</span> <span class="li-required">required: false</span></li>
    <li> <span class="li-head">refer_xss_detection</span> -  Switch of the Refer XSS detection (enable or disable). <span class="li-normal">type: str</span> <span class="li-required">required: false</span></li>
    <li> <span class="li-head">sql_exception_name</span> - Specify the name of exception in SQL detection.<span class="li-normal">type: str</span> <span class="li-required">required: false</span> </li>
    <li> <span class="li-head">sql_injection_action</span> - Specify the action after targets detected in SQL injection detection.<span class="li-normal">type: int</span> <span class="li-required">required: false</span> </li>
    <li> <span class="li-head">sql_injection_detection</span> -  Switch of the SQL injection detection (enable or disable). <span class="li-normal">type: str</span> <span class="li-required">required: false</span></li>
    <li> <span class="li-head">sql_injection_severity</span> -  Specify the severity after targets detected in SQL injection detection. <span class="li-normal">type: str</span> <span class="li-required">required: false</span></li>
    <li> <span class="li-head">uri_sql_injection_detection</span> -  Switch of the URI SQL injection detection (enable or disable). <span class="li-normal">type: str</span> <span class="li-required">required: false</span></li>
    <li> <span class="li-head">uri_xss_detection</span> -  Switch of the URI XSS detection (enable or disable). <span class="li-normal">type: str</span> <span class="li-required">required: false</span></li>
    <li> <span class="li-head">xss_action</span> -  Specify the action after targets detected in XSS detection. <span class="li-normal">type: str</span> <span class="li-required">required: false</span></li>
    <li> <span class="li-head">xss_detection</span> -  Switch of the XSS detection (enable or disable). <span class="li-normal">type: str</span> <span class="li-required">required: false</span></li>
    <li> <span class="li-head">xss_exception_name</span> -  Specify the name of exception in XSS detection. <span class="li-normal">type: str</span> <span class="li-required">required: false</span></li>
    <li> <span class="li-head">xss_severity</span> -  Specify the severity after targets detected in XSS detection. <span class="li-normal">type: str</span> <span class="li-required">required: false</span></li>
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
            - name: Add WAF sql_xss_injection_detection
              fadcos_waf_heuristic_sql_xss_injection_detection:
                action: add
                name: sqlt2
                body_sql_injection_detection: disable
                body_xss_detection: disable
                cookie_sql_injection_detection: disable
                cookie_xss_detection: disable
                refer_sql_injection_detection: disable
                xss_severity: low

            - name: Add WAF sql_xss_injection_detection
              fadcos_waf_heuristic_sql_xss_injection_detection:
                action: add
                name: sqlt1
                body_sql_injection_detection: enable
                body_xss_detection: disable
                cookie_sql_injection_detection: disable
                cookie_xss_detection: disable
                refer_sql_injection_detection: disable
                xss_severity: low

            - name: edit WAF sql_xss_injection_detection
              fadcos_waf_heuristic_sql_xss_injection_detection:
                action: edit
                name: sqlt2
                xss_severity: high
                cookie_xss_detection: enable

            - name: get WAF sql_xss_injection_detection
              fadcos_waf_heuristic_sql_xss_injection_detection:
                action: get
                name: sqlt2

            - name: delete WAF sql_xss_injection_detection
              fadcos_waf_heuristic_sql_xss_injection_detection:
                action: delete
                name: sqlt1
            
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
