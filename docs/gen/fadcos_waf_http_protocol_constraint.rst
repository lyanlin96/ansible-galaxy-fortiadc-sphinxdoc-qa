:source: fadcos_waf_http_protocol_constraint.py

:orphan:

.. fadcos_waf_http_protocol_constraint:

fadcos_waf_http_protocol_constraint -- Configuring an HTTP Protocol Constraint policy
++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++

.. versionadded:: 1.3.0

.. contents::
   :local:
   :depth: 1


Synopsis
--------
- Configuring an HTTP Protocol Constraint policy



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
 <td>fadcos_waf_http_protocol_constraint</td>
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
    <li> <span class="li-head">name</span> - Enter a unique HTTP protocol constraint policy name. <span class="li-normal">type: str</span> <span class="li-required">required: true</span> </li>
    <li> <span class="li-head">max_uri_length</span> - Maximum characters in an HTTP request URI. The default is 2048. The valid range is 1-8192.<span class="li-normal">type: str</span> <span class="li-required">required: false</span> </li>
    <li> <span class="li-head">max_uri_length_action</span> - Select the action profile that you want to apply for too many characters in an HTTP request URI. <span class="li-normal">type: str</span> <span class="li-required">required: true</span> </li>
    <li> <span class="li-head">max_uri_length_severity</span> - Set the severity level in WAF logs of the too large numbers of characters in an HTTP request URI.<span class="li-normal">type: str</span> <span class="li-required">required: true</span> </li>
    <li> <span class="li-head">max_url_param_name_len</span> - Maximum characters in a URL parameter name. The default is 1024. The valid range is 1-2048. <span class="li-normal">type: str</span> <span class="li-required">required: true</span> </li>
    <li> <span class="li-head">max_url_param_name_len_action</span> - Select the action profile that you want to apply for too many characters in a URL parameter name. <span class="li-normal">type: str</span> <span class="li-required">required: true</span> </li>
    <li> <span class="li-head">max_url_param_name_len_severity</span> - Set the severity level in WAF logs of a too large number of characters in a URL parameter name.<span class="li-normal">type: str</span> <span class="li-required">required: true</span> </li>
    <li> <span class="li-head">max_url_param_value_len</span> - Maximum characters in a URL parameter value. The default is 4096. The valid range is 1-8192.<span class="li-normal">type: str</span> <span class="li-required">required: true</span> </li>
    <li> <span class="li-head">illegal_host_name</span> - Enable/disable hostname checks.<span class="li-normal">type: int</span> <span class="li-required">required: false</span> </li>
    <li> <span class="li-head">illegal_host_name_action</span> - Select the action profile that you want to apply for hostname checks. <span class="li-normal">type: str</span> <span class="li-required">required: true</span> </li>
    <li> <span class="li-head">illegal_host_name_severity</span> - Set the severity level in WAF logs of the failed hostname checks. <span class="li-normal">type: str</span> <span class="li-required">required: true</span> </li>
    <li> <span class="li-head">illegal_http_version</span> - 	Enable/disable the HTTP version check. <span class="li-normal">type: str</span> <span class="li-required">required: false</span></li>
    <li> <span class="li-head">illegal_http_version_action</span> - Select the action profile that you want to apply for the HTTP version check. <span class="li-normal">type: str</span> <span class="li-required">required: true</span> </li>
    <li> <span class="li-head">illegal_http_version_severity</span> - Set the severity level in WAF logs of the failed HTTP version check. <span class="li-normal">type: str</span> <span class="li-required">required: true</span> </li>
    <li> <span class="li-head">illegal_multipart</span> - Enable/Disable the HTTP body multipart check. <span class="li-normal">type: str</span> <span class="li-required">required: true</span> </li>
    <li> <span class="li-head">illegal_multipart_action</span> - Select the action profile that you want to apply for the the HTTP body multipart check. <span class="li-normal">type: str</span> <span class="li-required">required: false</span> </li>
    <li> <span class="li-head">illegal_multipart_severity</span> - Set the severity level in WAF logs of the failed HTTP body multipart check. <span class="li-normal">type: str</span> <span class="li-required">required: false</span> </li>
    <li> <span class="li-head">max_cookie_number</span> - Maximum number of cookie headers in an HTTP request. <span class="li-normal">type: str</span> <span class="li-required">required: true</span> </li>
    <li> <span class="li-head">max_cookie_number_action</span> - Select the action profile that you want to apply for the oversized cookie headers. <span class="li-normal">type: str</span> <span class="li-required">required: true</span> </li>
    <li> <span class="li-head">max_cookie_number_severity</span> - Set the severity level in WAF logs of the oversized cookie headers. <span class="li-normal">type: str</span> <span class="li-required">required: true</span> </li>
    <li> <span class="li-head">max_header_number</span> - Maximum number of headers in an HTTP request. The default is 50. Requests with more headers are a symptom of a buffer overflow attack or an attempt to evade detection mechanisms. The valid configuration range is 1-100. <span class="li-normal">type: str</span> <span class="li-required">required: true</span> </li>
    <li> <span class="li-head">max_header_number_action</span> - Select the action profile that you want to apply when the number of headers in an HTTP request is too large. <span class="li-normal">type: str</span> <span class="li-required">required: false</span> </li>
    <li> <span class="li-head">max_header_number_severity</span> - Set the severity level in WAF logs of the too large numbers of headers in an HTTP request. <span class="li-normal">type: str</span> <span class="li-required">required: false</span> </li>
    <li> <span class="li-head">max_header_length</span> - Maximum length of the HTTP request header. The default is 8192. The valid range is 1-16384.<span class="li-normal">type: str</span> <span class="li-required">required: false</span> </li>
    <li> <span class="li-head">max_header_length_action</span> - Select the action profile that you want to apply for too long headers. <span class="li-normal">type: str</span> <span class="li-required">required: true</span> </li>
    <li> <span class="li-head">max_header_length_severity</span> - Set the severity level in WAF logs of too long headers in an HTTP request.<span class="li-normal">type: str</span> <span class="li-required">required: false</span></li>
    <li> <span class="li-head">max_req_hdr_name_len</span> - Maximum characters in an HTTP request header name. The default is 1024. The valid range is 1-8192.<span class="li-normal">type: int</span> <span class="li-required">required: false</span> </li>
    <li> <span class="li-head">max_req_hdr_name_len_action</span> - Select the action profile that you want to apply for too large numbers of characters in an HTTP request header name. <span class="li-normal">type: str</span> <span class="li-required">required: false</span> </li>
    <li> <span class="li-head">max_req_hdr_name_len_severity</span> - Set the severity level in WAF logs of the too large numbers of characters in an HTTP request header name. <span class="li-normal">type: str</span> <span class="li-required">required: false</span> </li>
    <li> <span class="li-head">max_req_hdr_value_len</span> - Maximum characters in an HTTP request header value. The default is 4096. Longer headers might be a symptom of a buffer overflow attack. The valid configuration range is 1-8192.<span class="li-normal">type: str</span> <span class="li-required">required: false</span></li>
    <li> <span class="li-head">max_body_length</span> - Maximum length of the HTTP body. The default is 67108864. The valid range is 1-67108864.<span class="li-normal">type: int</span> <span class="li-required">required: false</span> </li>
    <li> <span class="li-head">max_body_length_action</span> - Select the action profile that you want to apply for invalid HTTP body length. <span class="li-normal">type: str</span> <span class="li-required">required: true</span> </li>
    <li> <span class="li-head">max_body_length_severity</span> - Set the severity level in WAF logs of the failed HTTP body multipart check. <span class="li-normal">type: str</span> <span class="li-required">required: false</span> </li>
    <li> <span class="li-head">constraint_method_override</span> - 	Enable/Disable to scan request method and try to match it in request method rule in following override headers. <span class="li-normal">type: str</span> <span class="li-required">required: false</span></li>
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
            - name: Add WAF http_protocol_constraint
              fadcos_waf_http_protocol_constraint:
                action: add
                name: htest1
                constraint_method_override: disable
                illegal_host_name: disable
                illegal_host_name_action: alert
                illegal_host_name_severity: low
                illegal_http_version: disable
                illegal_http_version_action: alert
                illegal_http_version_severity: low
                illegal_multipart: disable
                illegal_multipart_action: alert
                illegal_multipart_severity: low
                max_body_length: 67108864
                max_body_length_action: alert
                max_body_length_severity: low
                max_cookie_number: 16
                max_cookie_number_action: alert
                max_cookie_number_severity: low
                max_header_length: 8192
                max_header_length_action: alert
                max_header_length_severity: low
                max_header_number: 50
                max_header_number_action: alert
                max_header_number_severity: low
                max_req_hdr_name_len: 1024
                max_req_hdr_name_len_action: alert
                max_req_hdr_name_len_severity: low
                max_req_hdr_value_len: 4096
                max_req_hdr_value_len_action: alert
                max_req_hdr_value_len_severity: low
                max_uri_length: 2048
                max_uri_length_action: deny
                max_uri_length_severity: low
                max_url_param_name_len: 1024
                max_url_param_name_len_action: alert
                max_url_param_name_len_severity: low
                max_url_param_value_len: 4096
                max_url_param_value_len_action: alert
                max_url_param_value_len_severity: low

            - name: get WAF http_protocol_constraint
              fadcos_waf_http_protocol_constraint:
                action: get
                name: htest1

            - name: edit WAF http_protocol_constraint
              fadcos_waf_http_protocol_constraint:
                action: edit
                name: htest1
                max_header_number: 88

            - name: delete WAF http_protocol_constraint
              fadcos_waf_http_protocol_constraint:
                action: delete
                name: HPC1
            
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
