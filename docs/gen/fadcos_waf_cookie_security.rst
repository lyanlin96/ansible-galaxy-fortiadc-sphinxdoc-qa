:source: fadcos_waf_cookie_security.py

:orphan:

.. fadcos_waf_cookie_security:

fadcos_waf_cookie_security -- Configure a Cookie Security policy
++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++

.. versionadded:: 1.3.0

.. contents::
   :local:
   :depth: 1


Synopsis
--------
- Configure a Cookie Security policy



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
 <td>fadcos_waf_cookie_security</td>
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
    <li> <span class="li-head">max_age</span> - Specify the maximum age (in minutes) if the response from the backend server does not already have a "Max-Age" attribute, or does not have an "Expires" attribute. <span class="li-normal">type: str</span> <span class="li-required">required: false</span> </li>
    <li> <span class="li-head">samesite</span> - Add SameSite attribute to prevent the browser from sending cookies along with cross-site requests, to mitigate the risk of cross-origin information leakage.<span class="li-normal">type: str</span> <span class="li-required">required: false</span> </li>
    <li> <span class="li-head">allow_suspicious_cookies</span> - Select whether or not FortiADC will allow requests that contain unrecognizable cookies or if there are missing cookies.<span class="li-normal">type: str</span> <span class="li-required">required: false</span> </li>
    <li> <span class="li-head">cookie_replay</span> - Disable or enable to allow FortiADC to use the IP address of a request to determine the owner of the cookie.<span class="li-normal">type: str</span> <span class="li-required">required: false</span> </li>
    <li> <span class="li-head">enc_cookie_type</span> - Specify how cookies are encrypted.<span class="li-normal">type: str</span> <span class="li-required">required: false</span> </li>
    <li> <span class="li-head">dont_blk_until</span> - Specify the date to begin blocking suspicious cookies.<span class="li-normal">type: str</span> <span class="li-required">required: false</span> </li>
    <li> <span class="li-head">exception</span> - Specify exceptions identifing specific patterns that are not subject to processing by WAF rules.<span class="li-normal">type: str</span> <span class="li-required">required: false</span> </li>
    <li> <span class="li-head">http_only</span> - Enable to add "HTTPOnly" flag to cookies.<span class="li-normal">type: str</span> <span class="li-required">required: false</span> </li>
    <li> <span class="li-head">rm_cookie</span> - Enable so FortiADC will accept the request, but will also remove the cookie before sending it to backend web server.<span class="li-normal">type: str</span> <span class="li-required">required: false</span> </li>
    <li> <span class="li-head">sec_mode</span> - Specify a security mode ("no", "signed", or "encrypted").<span class="li-normal">type: str</span> <span class="li-required">required: false</span> </li>
    <li> <span class="li-head">security_action</span> - Select the action to apply.<span class="li-normal">type: str</span> <span class="li-required">required: false</span> </li>
    <li> <span class="li-head">secure</span> - Enable to add the secure flag to cookies.<span class="li-normal">type: str</span> <span class="li-required">required: false</span> </li>
    <li> <span class="li-head">severity</span> - Select which severity level FortiADC uses when using Cookie Security.<span class="li-normal">type: str</span> <span class="li-required">required: false</span> </li>
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
            - name: Add cookie_security
              fadcos_waf_cookie_security:
                action: add
                name: ck1
            - name: Add cookie_security again
              fadcos_waf_cookie_security:
                action: add
                name: ck1
            - name: edit acookie_security
              fadcos_waf_cookie_security:
                action: edit
                name: ck1
                max_age: 250
                samesite: lax
            - name: get acookie_security
              fadcos_waf_cookie_security:
                action: get
                name: ck1
            - name: delete cookie security
              fadcos_waf_cookie_security:
                action: delete
                name: ck1  
    
            
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
