:source: fadcos_waf_api_gateway_rule.py

:orphan:

.. fadcos_waf_api_gateway_rule:

fadcos_waf_api_gateway_rule -- Configure rule objects of an API Gateway policy
++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++

.. versionadded:: 1.3.0

.. contents::
   :local:
   :depth: 1


Synopsis
--------
- Configure rule objects of an API Gateway policy



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
 <td>fadcos_waf_api_gateway_rule</td>
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
    <li> <span class="li-head">name</span> - Specify the name of the API gateway rule. <span class="li-normal">type: str</span> <span class="li-required">required: true</span> </li>
    <li> <span class="li-head">host</span> - Select the name of a protected host that the Host.<span class="li-normal">type: str</span> <span class="li-required">required: false</span> </li>
    <li> <span class="li-head">host_status</span> - Enable/Disable for applying this rule only to HTTP requests for specific web hosts.<span class="li-normal">type: str</span> <span class="li-required">required: false</span> </li>
    <li> <span class="li-head">security_action</span> - Select the action profile that you want to apply.<span class="li-normal">type: str</span> <span class="li-required">required: false</span> </li>
    <li> <span class="li-head">location</span> - Indicate where to find the API key in HTTP request ("http-header" or "http-parameter").<span class="li-normal">type: str</span> <span class="li-required">required: false</span> </li>
    <li> <span class="li-head">method</span> - Select one or more HTTP methods are allowed when access the API.<span class="li-normal">type: str</span> <span class="li-required">required: false</span> </li>
    <li> <span class="li-head">parameter_name</span> - Specify the HTTP parameter name of the API key. <span class="li-normal">type: str</span> <span class="li-required">required: false</span> </li>
    <li> <span class="li-head">field_name</span> - Specify the header filed name of the API key. <span class="li-normal">type: str</span> <span class="li-required">required: false</span> </li>
    <li> <span class="li-head">rlimit_period</span> - Sets the time spent during which to count how many times a request is received.<span class="li-normal">type: str</span> <span class="li-required">required: false</span> </li>
    <li> <span class="li-head">rlimit_reqs</span> - Sets the condition for the limit of the number of API requests received.<span class="li-normal">type: str</span> <span class="li-required">required: false</span> </li>
    <li> <span class="li-head">rlimit_status</span> - Enable/Disable to do rate limit for API calls.<span class="li-normal">type: str</span> <span class="li-required">required: false</span> </li>
    <li> <span class="li-head">severity</span> - Select which severity level FortiADC uses when using Input Validation.<span class="li-normal">type: str</span> <span class="li-required">required: false</span> </li>
    <li> <span class="li-head">verification</span> - When a user makes an API request, the API key will be included in the HTTP header or parameter.<span class="li-normal">type: str</span> <span class="li-required">required: false</span> </li> 
    <li> <span class="li-head">url_pattern</span> - Matching string. Regular expressions are supported.<span class="li-normal">type: str</span> <span class="li-required">required: false</span> </li> 
    <li> <span class="li-head">exception</span> - Select a user-defined exception configuration object.<span class="li-normal">type: str</span> <span class="li-required">required: false</span> </li>   
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
            - name: Add waf_api_gateway_rule
              fadcos_waf_api_gateway_rule:
                action: add
                name: test_rule1
                security_action: alert
                host: host1
                host_status: enable
                location: http-parameter
                method: GET POST HEAD OPTIONS TRACE CONNECT DELETE PUT PATCH OTHER
                parameter_name: acc
                rlimit_period: 60
                rlimit_reqs: 600
                rlimit_status: enable
                severity: low
                url_pattern: /home/test
                verification: enable

            - name: edit waf_api_gateway_rule
              fadcos_waf_api_gateway_rule:
                action: edit
                name: test_rule1
                parameter_name: add
                severity: high
                url_pattern: /home/qqq

            - name: Add waf_api_gateway_rule
              fadcos_waf_api_gateway_rule:
                action: add
                name: test_rule1
                security_action: alert

            - name: get waf_api_gateway_rule
              fadcos_waf_api_gateway_rule:
                action: get
                name: test_rule1

            - name: delete waf_api_gateway_rule
              fadcos_waf_api_gateway_rule:
                action: delete
                name: agr1

            - name: delete waf_api_gateway_rule
              fadcos_waf_api_gateway_rule:
                action: delete
                name: agr1
            
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
