:source: fadcos_waf_http_header_security_child_rule_list.py

:orphan:

.. fadcos_waf_http_header_security_child_rule_list:

fadcos_waf_http_header_security_child_rule_list -- Configure the HTTP Header Security Rules section of an HTTP Header Security policy
++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++

.. versionadded:: 1.3.0

.. contents::
   :local:
   :depth: 1


Synopsis
--------
- Configure the HTTP Header Security Rules section of an HTTP Header Security policy



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
 <td>fadcos_waf_http_header_security_child_rule_list</td>
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
    <li> <span class="li-head">name</span> - Specify the HTTP Header Security policy name. <span class="li-normal">type: str</span> <span class="li-required">required: true</span> </li>
    <li> <span class="li-head">include_subdomain</span> - Optional. If enabled, rule will apply to all of the site's subdomains as well.<span class="li-normal">type: str</span> <span class="li-required">required: false</span> </li>
    <li> <span class="li-head">max_age</span> - The time, in seconds, that the browser should remember that a site is only to be accessed using HTTPS. <span class="li-normal">type: int</span> <span class="li-required">required: false</span> </li>
    <li> <span class="li-head">id</span> - Specify the ID of rule setting of the HTTP security header. <span class="li-normal">type: str</span> <span class="li-required">required: false</span></li>
    <li> <span class="li-head">rule_name</span> - Select the HTTP security header name (content-security-policy, x-content-type-options, x-frame-options, x-xss-protection, and http-strict-transport-security).<span class="li-normal">type: str</span> <span class="li-required">required: false</span> </li>
    <li> <span class="li-head">preload</span> - Google maintains an HSTS preload service. By following the guidelines and successfully submitting your domain, browsers will never connect to your domain using an insecure connection. While the service is hosted by Google, all browsers have stated an intent to use (or actually started using) the preload list. Most major browsers (Chrome, Firefox, Opera, Safari, IE 11 and Edge) also have HSTS preload lists based on the Chrome list. (See the HSTS compatibility matrix.) However, it is not part of the HSTS specification and should not be treated as official.<span class="li-normal">type: int</span> <span class="li-required">required: false</span> </li>
    <li> <span class="li-head">policy</span> - The Policy option is available if the Name is content-security-policy. Enter the header value(s) that setting restrictions on resource types and sources. For example, default-src 'self';script-src 'self';object-src 'self'. <span class="li-normal">type: str</span> <span class="li-required">required: false</span></li>
    <li> <span class="li-head">report_only</span> - Enabling report-only switches to “Content-Security-Policy-Report-Only” header, which accepts all directives of CSP. However, “report-only” header only monitors the violations. FortiADC will check the existing of “report-uri” directive once “report-only” selected. <span class="li-normal">type: str</span> <span class="li-required">required: false</span></li>
    <li> <span class="li-head">value</span> - Specify the HTTP header value. <span class="li-normal">type: str</span> <span class="li-required">required: false</span></li>
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
            - name: Add waf_http_header_security_child_rule_list
              fadcos_waf_http_header_security_child_rule_list:
                action: add
                name: hts1
                include_subdomain: disable
                max_age: 31536000
                rule_name: x-xss-protection
                preload: disable
                report_only: disable
                value: block-mode

            - name: edit waf_http_header_security_child_rule_list
              fadcos_waf_http_header_security_child_rule_list:
                action: edit
                name: hts1
                id: 1
                include_subdomain: disable
                rule_name: content-security-policy
                policy: p1

            - name: get waf_http_header_security_child_rule_list
              fadcos_waf_http_header_security_child_rule_list:
                action: edit
                name: hts1
                id: 1

            - name: delete waf_http_header_security_child_rule_list
              fadcos_waf_http_header_security_child_rule_list:
                action: delete
                name: hts1
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
