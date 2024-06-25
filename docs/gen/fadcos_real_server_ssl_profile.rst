:source: fadcos_real_server_ssl_profile.py

:orphan:

.. fadcos_real_server_ssl_profile:

fadcos_real_server_ssl_profile -- real server ssl profile configuration in Fortinet's FortiADC
++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++

.. versionadded:: 1.0.0

.. contents::
   :local:
   :depth: 1


Synopsis
--------
- Configure FortiADC real server ssl profile



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
 <td><code class="docutils literal notranslate">v7.0.0 </code></td>
 <td><code class="docutils literal notranslate">v7.0.1 </code></td>
 <td><code class="docutils literal notranslate">v7.0.2 </code></td>
 <td><code class="docutils literal notranslate">v7.1.0 </code></td>
 <td><code class="docutils literal notranslate">v7.1.4 </code></td>
 <td><code class="docutils literal notranslate">v7.2.2 </code></td>
 <td><code class="docutils literal notranslate">v7.4.0 </code></td>
 </tr>
 <tr>
 <td>fortiadc_real_server_ssl_profile</td>
 <td>yes</td>
 <td>yes</td>
 <td>yes</td>
 <td>yes</td>
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
    <li> <span class="li-head">action</span> - Type of action to perform on the object.<span class="li-normal">type: str</span> <span class="li-required">required: true</span></li>
    <li> <span class="li-head">name</span> - Real server SSL profile object name.<span class="li-normal">type: str</span> <span class="li-required">required: true</span> </li>
    <li> <span class="li-head">allow_ssl_versions</span> - Allowed SSL version.<span class="li-normal">type: str</span> <span class="li-required">required: false</span> <span class="li-normal">default: sslv3 tlsv1.0 tlsv1.1 tlsv1.2</span> </li>
    <li> <span class="li-head">ciphers_tlsv13</span> - TLSv1.3 ciphers.<span class="li-normal">type: str</span> <span class="li-required">required: false</span> </li>
    <li> <span class="li-head">customized_ssl_ciphers_flag</span> - Enable/disable use of user-specified cipher suites. When enabled, you must select a Customized SSL Cipher.<span class="li-normal">type: str</span> <span class="li-required">required: false</span> <span class="li-normal">default: disable</span> </li>
    <li> <span class="li-head">new_ssl_ciphers_long</span> - If the customize cipher flag is enabled, specify a colon-separated, ordered list of cipher suites. An empty string is allowed. If empty, the default cipher suite list is used.<span class="li-normal">type: List</span> <span class="li-required">required: false</span> </li>
    <li> <span class="li-head">renegotiate_period</span> - Specify the interval from the initial connect time that FortiADC renegotiates an SSL session. The unit of measurement canbe second (default), minute, or hour, e.g., 100s, 20m, or 1h.<span class="li-normal">type: str</span> <span class="li-required">required: false</span> <span class="li-normal">default: 0</span> </li>
    <li> <span class="li-head">renegotiate_size</span> - Specify the amount (in MB) of application data that must have been transmitted over the secure connection before FortiADC initiates the renegotiation of an SSL session.<span class="li-normal">type: str</span> <span class="li-required">required: false</span> <span class="li-normal">default: 0</span> </li>
    <li> <span class="li-head">renegotiation</span> - This option controls how FortiADC responds to mid-stream SSL reconnection requests either initiated by real servers or forced by FortiADC.<span class="li-normal">type: str</span> <span class="li-required">required: false</span> <span class="li-normal">default: enable</span> </li>
    <li> <span class="li-head">renegotiation_deny_action</span> - This option becomes available when Renegotiation is disabled on the server side. In that case, you must select an action that FortiADC will take when denying an SSL renegotiation request: ignore or terminate.<span class="li-normal">type: str</span> <span class="li-required">required: false</span> <span class="li-normal">default: ignore</span> </li>
    <li> <span class="li-head">secure_renegotiation</span> - Secure renegotiation of SSL connections. (request/require/require_strict)<span class="li-normal">type: str</span> <span class="li-required">required: false</span> <span class="li-normal">default: require</span> </li>
    <li> <span class="li-head">server_OCSP_stapling</span> - Enable/disable server side OCSP stapling.<span class="li-normal">type: str</span> <span class="li-required">required: false</span> <span class="li-normal">default: disable</span> </li>
    <li> <span class="li-head">session_reuse_flag</span> - Enable/disable SSL session reuse.<span class="li-normal">type: str</span> <span class="li-required">required: false</span> <span class="li-normal">default: disable</span> </li>
    <li> <span class="li-head">session_reuse_limit</span> - Session reuse limit, the default is 0 (disabled). The valid range is 0-1048576.<span class="li-normal">type: str</span> <span class="li-required">required: false</span> <span class="li-normal">default: 0</span> </li>
    <li> <span class="li-head">sni_forward_flag</span> - Enable/disable forwarding the client SNI value to the server. The SNI value will be forwarded to the real server only when the client-side ClientHello message contains a valid SNI value; otherwise, nothing is forwarded.<span class="li-normal">type: str</span> <span class="li-required">required: false</span> <span class="li-normal">default: disable</span> </li>
    <li> <span class="li-head">ssl</span> - Enable/disable SSL for the connection between the FortiADC and the real server.<span class="li-normal">type: str</span> <span class="li-required">required: false</span> <span class="li-normal">default: disable</span> </li>
    <li> <span class="li-head">tls_ticket_flag</span> - Enable/disable TLS ticket-based session reuse.<span class="li-normal">type: str</span> <span class="li-required">required: false</span> <span class="li-normal">default: disable</span> </li>
    <li> <span class="li-head">local_cert</span> - Select a local certificate.<span class="li-normal">type: str</span> <span class="li-required">required: false</span> <span class="li-normal">default: Factory</span> </li>
    <li> <span class="li-head">cert_verify</span> - Specify a Certificate Verify configuration object to validate server certificates. This Certificate Verify object must include a CA group and may include OCSP and CRL checks.<span class="li-normal">type: str</span> <span class="li-required">required: false</span> </li>
    <li> <span class="li-head">vdom</span> - VDOM name if enabled.<span class="li-normal">type: str</span> <span class="li-required">required: true(if VDOM is enabled)</li>
    </ul>


Examples
--------

.. code-block:: yaml+jinja

	- name:
	  hosts: all
	  connection: httpapi
	  gather_facts: false
	  tasks:
		- name: Manage Real Server SSL Profile
		  fadcos_real_server_ssl_profile:
			action: add
			name: ansible_test_server_ssl


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

- Jie Li
- Aravindh Sri


.. hint::
    If you notice any issues in this documentation, you can create a pull request to improve it.
