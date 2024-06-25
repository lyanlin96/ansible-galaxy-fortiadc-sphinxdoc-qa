:source: fadcos_client_ssl_profile.py

:orphan:

.. fadcos_client_ssl_profile:

fadcos_client_ssl_profile -- client ssl profile configuration in Fortinet's FortiADC
++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++

.. versionadded:: 1.0.0

.. contents::
   :local:
   :depth: 1


Synopsis
--------
- Configure FortiADC client ssl profile



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
 <td>fortiadc_client_ssl_profile</td>
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
    <li> <span class="li-head">action</span> - Type of action to perform on the object.<span class="li-normal">type: str</span> <span class="li-required">required: true</span> </li>
    <li> <span class="li-head">name</span> - Client SSL Profile name.<span class="li-normal">type: str</span> <span class="li-required">required: true</span> </li>
    <li> <span class="li-head">backend_ciphers_tlsv13</span> - TLSv1.3 ciphers, only available if the backendTLSv1.3 is enabled.<span class="li-normal">type: str</span> <span class="li-required">required: false</span></li>
    <li> <span class="li-head">backend_customized_ssl_ciphers_flag</span> - Enabled by default. You must specify the backend customized SSL ciphers.<span class="li-normal">type: str</span> <span class="li-required">required: false</span> <span class="li-normal">default: enalbe</span> </li>
    <li> <span class="li-head">backend_ssl_OCSP_stapling_support</span> - Enable it to let FortiADC support OCSP stapling at the backend.<span class="li-normal">type: str</span> <span class="li-required">required: false</span> <span class="li-normal">default: disable</span> </li>
    <li> <span class="li-head">backend_ssl_allowed_versions</span> - Supported backend SSL versions.<span class="li-normal">type: str</span> <span class="li-required">required: false</span> <span class="li-normal">default: sslv3 tlsv1.0 tlsv1.1 tlsv1.2</span> </li>
    <li> <span class="li-head">backend_ssl_ciphers</span> - Backend SSL cipher suite.<span class="li-normal">type: str</span> <span class="li-required">required: false</span></li>
    <li> <span class="li-head">backend_ssl_sni_forward</span> - Enable it to let FortiADC forward Server Name Indication (SNI) from the client to the backend.<span class="li-normal">type: str</span> <span class="li-required">required: false</span> <span class="li-normal">default: disable</span> </li>
    <li> <span class="li-head">client_certificate_verify</span> - The client certificate verify configuration object.<span class="li-normal">type: str</span> <span class="li-required">required: false</span></li>
    <li> <span class="li-head">client_certificate_verify_mode</span> - Available only when the Client Certificate Verify is selected. Required by default.<span class="li-normal">type: str</span> <span class="li-required">required: false</span> <span class="li-normal">default: required</span> </li>
    <li> <span class="li-head">client_sni_required</span> - Require clients to use the TLS server name indication (SNI) extension to include the server hostname in the TLS client hello message. Then, the FortiADC system can select the appropriate local server certificate to present to the client.<span class="li-normal">type: str</span> <span class="li-required">required: false</span> <span class="li-normal">default: disable</span> </li>
    <li> <span class="li-head">customized_ssl_ciphers_flag</span> - Enable or disable the use of user-specified cipher suites. If enabled, you must specify an ordered list of a customized SSL cipher suites.<span class="li-normal">type: str</span> <span class="li-required">required: false</span> <span class="li-normal">default: disable</span> </li>
    <li> <span class="li-head">forward_proxy</span> - By default, (SSL) Forward Proxy is disabled. When enabled, you'll have to configure additional settings noted below.<span class="li-normal">type: str</span> <span class="li-required">required: false</span> <span class="li-normal">default: disable</span> </li>
    <li> <span class="li-head">forward_proxy_certificate_caching</span> - Select a Forward Proxy Certificate Caching rule.<span class="li-normal">type: str</span> <span class="li-required">required: false</span> </li>
    <li> <span class="li-head">forward_proxy_intermediate_ca_group</span> - Select a Forward Proxy Intermediate CA Group.<span class="li-normal">type: str</span> <span class="li-required">required: false</span> </li>
    <li> <span class="li-head">forward_proxy_local_signing_ca</span> - Select a Forward Proxy Local Signing CA.<span class="li-normal">type: str</span> <span class="li-required">required: false</span> <span class="li-normal">default: SSLPROXY_LOCAL_CA</span> </li>
    <li> <span class="li-head">http_forward_client_certificate</span> - Disabled by default. When enabled, you must specify the client certificate forward header.<span class="li-normal">type: str</span> <span class="li-required">required: false</span> <span class="li-normal">default:disable </span> </li>
    <li> <span class="li-head">http_forward_client_certificate_header</span> - When Client Certificate Forward is enabled, specify the client certificate forward header.<span class="li-normal">type: str</span> <span class="li-required">required: false</span> <span class="li-normal">default: X-Client-Cert</span> </li>
    <li> <span class="li-head">local_certificate_group</span> - Select a local certificate group that includes the certificates this virtual server presents to SSL/TLS clients. This should be the backend servers' certificate.<span class="li-normal">type: str</span> <span class="li-required">required: false</span> <span class="li-normal">default: LOCAL_CERT_GROUP</span> </li>
    <li> <span class="li-head">reject_ocsp_stapling_with_missing_nextupdate</span> - This flag is meaningful only when you have configured OCSP stapling in Local Certificate Group.<span class="li-normal">type: str</span> <span class="li-required">required: false</span> <span class="li-normal">default: disable</span> </li>
    <li> <span class="li-head">ssl_allowed_versions</span> - Allowed SSL versions.<span class="li-normal">type: str</span> <span class="li-required">required: false</span> <span class="li-normal">default: tlsv1.1 tlsv1.2</span> </li>
    <li> <span class="li-head">ssl_ciphers</span> - SSL cipher suite.<span class="li-normal">type: str</span> <span class="li-required">required: false</span></li>
    <li> <span class="li-head">ssl_ciphers_tlsv13</span> - TLS v1.3 Cipher suite.<span class="li-normal">type: str</span> <span class="li-required">required: false</span> </li>
    <li> <span class="li-head">ssl_dh_param_size</span> - Specify the pubkey length in Diffie Hellman.<span class="li-normal">type: str</span> <span class="li-required">required: false</span> <span class="li-normal">default: 1024bit</span> </li>
    <li> <span class="li-head">ssl_dynamic_record_sizing</span> - Allows ADC to dynamically adjust the size of TLS records based on the state of the connection, in order to prevent bottlenecks caused by the buffering of TLS record fragments.<span class="li-normal">type: str</span> <span class="li-required">required: false</span> <span class="li-normal">default: disable</span> </li>
    <li> <span class="li-head">ssl_renegotiate_period</span> - Specify the period in second (default), minute, or hour at which FortiADC will initiate SSL renegotiation.<span class="li-normal">type: str</span> <span class="li-required">required: false</span> <span class="li-normal">default: 0</span> </li>
    <li> <span class="li-head">ssl_renegotiate_size</span> - Specify the amount (MB) of application data that must have been transmitted over the SSL connection whenFortiADC initiates SSL renegotiation.<span class="li-normal">type: str</span> <span class="li-required">required: false</span> <span class="li-normal">default: 0</span> </li>
    <li> <span class="li-head">ssl_renegotiation</span> - Enable or disable SSL renegotiation from the client side.<span class="li-normal">type: str</span> <span class="li-required">required: false</span> <span class="li-normal">default: disable</span> </li>
    <li> <span class="li-head">ssl_renegotiation_interval</span> - Specify the minimum interval between two successive client-initiated SSL renegotiation requests. The unit of measurement can be second, minute, or hour, e.g., 100s, 20m, or 1h.<span class="li-normal">type: str</span> <span class="li-required">required: false</span> <span class="li-normal">default: -1</span> </li>
    <li> <span class="li-head">ssl_secure_renegotiation</span> - Secure renegotiation of SSL connections.<span class="li-normal">type: str</span> <span class="li-required">required: false</span> <span class="li-normal">default: require</span> </li>
    <li> <span class="li-head">ssl_session_cache_flag</span> - Allows to the same SSL client attempts to reconnect to this SSL server and requests a resumption of a previous SSL session.<span class="li-normal">type: str</span> <span class="li-required">required: false</span> <span class="li-normal">default: enable</span> </li>
    <li> <span class="li-head">use_tls_tickets</span> - Allows resuming TLS sessions by storing key material encrypted on the clients.<span class="li-normal">type: str</span> <span class="li-required">required: false</span> <span class="li-normal">default: enable</span> </li>
    <li> <span class="li-head">vdom</span> - VDOM name if enabled.<span class="li-normal">type: str</span> <span class="li-required">required: Yes (if VDOM is enabled)</span></li>
    </ul>


Examples
--------

.. code-block:: yaml+jinja

	- name:
	  hosts: all
	  connection: httpapi
	  gather_facts: false
	  tasks:
		- name: Manage Client SSL Profile
		  fadcos_client_ssl_profile:
			action: add
			name: test_client_ssl_profile


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
