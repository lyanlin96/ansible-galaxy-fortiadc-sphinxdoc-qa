:source: fadcos_waf_xml_validation_detection.py

:orphan:

.. fadcos_waf_xml_validation_detection:

fadcos_waf_xml_validation_detection -- Configuring XML Detection
++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++

.. versionadded:: 1.3.0

.. contents::
   :local:
   :depth: 1


Synopsis
--------
- Configuring XML Detection



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
 <td>fadcos_waf_xml_validation_detection</td>
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
    <li> <span class="li-head">name</span> - Enter the name of the XML Detection profile. You will use the name to select the XML Detection profile in WAF profiles. No spaces. <span class="li-normal">type: str</span> <span class="li-required">required: true</span> </li>
    <li> <span class="li-head">xml_format_checks</span> - Enter the name of the XML Detection profile. You will use the name to select the XML Detection profile in WAF profiles. No spaces. <span class="li-normal">type: str</span> <span class="li-required">required: true</span> </li>
    <li> <span class="li-head">soap_format_checks</span> - Enable or disable Soap Format Check.<span class="li-normal">type: str</span> <span class="li-required">required: false</span> </li>
    <li> <span class="li-head">soap_wsdl_checks</span> - Enable or disable WSDL Check.<span class="li-normal">type: int</span> <span class="li-required">required: false</span> </li>
    <li> <span class="li-head">xml_schema_checks</span> - Enable or disable XML Schema Check. <span class="li-normal">type: str</span> <span class="li-required">required: false</span></li>
    <li> <span class="li-head">xml_schema_id</span> - Select the XML schema file that you want to use to check whether XML content is valid. <span class="li-normal">type: str</span> <span class="li-required">required: true</span> </li>
    <li> <span class="li-head">soap_wsdl_id</span> -	Select a WSDL file from the list menu, which shows all WSDL files that are shown (uploaded) on the WSDL page. <span class="li-normal">type: str</span> <span class="li-required">required: true</span> </li>
    <li> <span class="li-head">xml_limit_checks</span> - Enable to enforce parsing limits to protect web servers from DOS attacks, including XML bombs and transform injections. <span class="li-normal">type: str</span> <span class="li-required">required: false</span> </li>
    <li> <span class="li-head">limit_max_attr</span> - Limits the maximum number of attributes each individual element is allowed to have. Available only when XML Limit Checks is enabled.<span class="li-normal">type: int</span> <span class="li-required">required: false</span> </li>
    <li> <span class="li-head">limit_max_attr_name_len</span> - Limits the maximum length of each attribute name. The default value is 128. The valid range is 1–2048. Available only when XML Limit Checks is enabled. <span class="li-normal">type: str</span> <span class="li-required">required: false</span></li>
    <li> <span class="li-head">limit_max_attr_value_len</span> - Limits the maximum length of each attribute value. The default value is 128. The valid range is 1–2048. Available only when XML Limit Checks is enabled. <span class="li-normal">type: str</span> <span class="li-required">required: true</span> </li>
    <li> <span class="li-head">limit_max_cdata_len</span> - Limits the length of the CDATA section for each element. The default value is 65535. The valid range is 1–65535. Available only when XML Limit Checks is enabled. <span class="li-normal">type: str</span> <span class="li-required">required: true</span> </li>
    <li> <span class="li-head">limit_max_elem_child</span> - Limits the maximum number of children each element is allowed, and includes other elements and character information. The default value is 65535. The valid range is 1–65535. Available only when XML Limit Checks is enabled.<span class="li-normal">type: str</span> <span class="li-required">required: false</span> </li>
    <li> <span class="li-head">limit_max_elem_depth</span> - Limits the maximum number of nested levels in each element. The default value is 256. The valid range is 1–65535. Available only when XML Limit Checks is enabled.<span class="li-normal">type: int</span> <span class="li-required">required: false</span> </li>
    <li> <span class="li-head">limit_max_elem_name_len</span> - Limits the maximum length of the name of each element. The default value is 128. The valid range is 1–65535. Available only when XML Limit Checks is enabled.<span class="li-normal">type: str</span> <span class="li-required">required: false</span></li>
    <li> <span class="li-head">limit_max_namespace</span> - Limits the number of namespace declarations in the XML document. The default value is 16. The valid range is 0–256. Available only when XML Limit Checks is enabled. <span class="li-normal">type: str</span> <span class="li-required">required: true</span> </li>
    <li> <span class="li-head">limit_max_namespace_uri_len</span> - Limits the URI length for each namespace declaration. The default value is 256. The valid range is 0–1024. Available only when XML Limit Checks is enabled. <span class="li-normal">type: str</span> <span class="li-required">required: true</span> </li>
    <li> <span class="li-head">xml_xss_checks</span> - Enable to examine the bodies of incoming XML requests that might indicate possible cross-site scripting attacks. <span class="li-normal">type: str</span> <span class="li-required">required: true</span> </li>
    <li> <span class="li-head">xml_sql_injection_checks</span> - Enable to examine bodies of incoming requests for inappropriate SQL characters and keywords that might indicate an SQL injection attack.  <span class="li-normal">type: str</span> <span class="li-required">required: true</span> </li>
    <li> <span class="li-head">severity</span> - Set the severity level in WAF logs of potential attacks detected by the XML Detection profile. <span class="li-normal">type: str</span> <span class="li-required">required: true</span> </li>
    <li> <span class="li-head">security_action</span> - Select the action profile that you want to apply. <span class="li-normal">type: str</span> <span class="li-required">required: true</span> </li>
    <li> <span class="li-head">exception_id</span> - Optional. Select the exception profile that you want to apply to the XML Detection profile. <span class="li-normal">type: str</span> <span class="li-required">required: true</span> </li>
    <li> <span class="li-head">action</span> - Type of action to perform on the object. <span class="li-normal">type: str</span> <span class="li-required">required: true</span> </li>
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
            - name: Add WAF xml_validation_detection
              fadcos_waf_xml_validation_detection:
                action: add
                name: xxx2
                limit_max_attr: 256
                limit_max_attr_name_len: 128
                limit_max_attr_value_len: 128
                limit_max_cdata_len: 65535
                limit_max_elem_child: 65535
                limit_max_elem_depth: 256
                limit_max_elem_name_len: 128
                limit_max_namespace: 16
                limit_max_namespace_uri_len: 256
                severity: low
                soap_format_checks: enable
                soap_wsdl_checks: enable
                xml_format_checks: enable
                xml_limit_checks: enable
                xml_schema_checks: enable

            - name: edit WAF xml_validation_detection
              fadcos_waf_xml_validation_detection:
                action: edit
                name: xxx2
                limit_max_attr: 200
                limit_max_attr_name_len: 200  
                limit_max_attr_value_len: 200
                security_action: block

            - name: get WAF xml_validation_detection
              fadcos_waf_xml_validation_detection:
                action: get
                name: xxx2

            - name: delete WAF xml_validation_detection
              fadcos_waf_xml_validation_detection:
                action: delete
                name: xxx1
            
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
