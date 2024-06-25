:source: fadcos_health_check.py

:orphan:

.. fadcos_health_check:

fadcos_health_check -- health check configuration in Fortinet's FortiADC
++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++

.. versionadded:: 1.0.0

.. contents::
   :local:
   :depth: 1


Synopsis
--------
- Configure FortiADC health check



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
 <td>fortiadc_health_check</td>
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
    <li> <span class="li-head">action</span> - Type of action to perform on the object<span class="li-normal">type: str</span> <span class="li-required">required: true</span> </li>
    <li> <span class="li-head">addr_type</span> - Type of address (IPv4/IPv6)<span class="li-normal">type: str</span> <span class="li-required">required: false</span> <span class="li-normal">default: ipv4</span> </li>
    <li> <span class="li-head">agent_type</span> - SNMP agent type<span class="li-normal">type: str</span> <span class="li-required">required: false</span> <span class="li-normal">default: UCD</span> </li>
    <li> <span class="li-head">acct_appid</span> - Specify the type Unsigned32 accounting application ID used to advertise support of the accounting portion of an application.<span class="li-normal">type: str</span> <span class="li-required">required: false</span> <span class="li-normal">default: 0</span> </li>
    <li> <span class="li-head">auth_appid</span> - Specify the type Unsigned32 authentication application ID used to advertise support of the authentication and authorization portion of an application.<span class="li-normal">type: str</span> <span class="li-required">required: false</span> <span class="li-normal">default: 0</span> </li>
    <li> <span class="li-head">allow_ssl_version</span> - Allowed SSL versions<span class="li-normal">type: str</span> <span class="li-required">required: false</span> <span class="li-normal">default: sslv3 tlsv1.0 tlsv1.1 tlsv1.2</span> </li>
    <li> <span class="li-head">attribute</span> - Attributes for the LDAP health check object.<span class="li-normal">type: str</span> <span class="li-required">required: false</span> </li>
    <li> <span class="li-head">basedn</span> - The distinguished name where a LDAP server will search from.<span class="li-normal">type: str</span> <span class="li-required">required: false</span> </li>
    <li> <span class="li-head">binddn</span> - The distinguished name used to bind to a LDAP server.<span class="li-normal">type: str</span> <span class="li-required">required: false</span></li>
    <li> <span class="li-head">column</span> - The column in which the send string (command) takes effect<span class="li-normal">type: str</span> <span class="li-required">required: false</span> </li>
    <li> <span class="li-head">community</span> - Must match the SNMP community string set on the backend server. If this does not match, all SNMP health checks fail.<span class="li-normal">type: str</span> <span class="li-required">required: false</span> </li>
    <li> <span class="li-head">compare_type</span> - SNMP compare type<span class="li-normal">type: str</span> <span class="li-required">required: false</span> <span class="li-normal">default: less</span> </li>
    <li> <span class="li-head">connect_type</span> - Oracle connect type<span class="li-normal">type: str</span> <span class="li-required">required: false</span> <span class="li-normal">default: service_name</span> </li>
    <li> <span class="li-head">cpu</span> - Maximum normal CPU usage. If overburdened, the health check fails.<span class="li-normal">type: str</span> <span class="li-required">required: false</span> <span class="li-normal">default: 96</span> </li>
    <li> <span class="li-head">cpu_weight</span> - CPU Weight<span class="li-normal">type: str</span> <span class="li-required">required: false</span> <span class="li-normal">default: 100</span> </li>
    <li> <span class="li-head">database</span> - Database<span class="li-normal">type: str</span> <span class="li-required">required: false</span> </li>
    <li> <span class="li-head">dest_addr</span> - IP address to send health check traffic.<span class="li-normal">type: str</span> <span class="li-required">required: false</span> <span class="li-normal">default: 0.0.0.0</span> </li>
    <li> <span class="li-head">dest_addr6</span> - IP address to send health check traffic.<span class="li-normal">type: str</span> <span class="li-required">required: false</span> <span class="li-normal">default: ::</span> </li>
    <li> <span class="li-head">dest_addr_type</span> - Destination address IP type.<span class="li-normal">type: str</span> <span class="li-required">required: false</span> <span class="li-normal">default: ipv4</span> </li>
    <li> <span class="li-head">disk</span> - Maximum normal disk usage. If the disk is too full, the health check fails.<span class="li-normal">type: str</span> <span class="li-required">required: false</span> <span class="li-normal">default: 96</span> </li>
    <li> <span class="li-head">disk_weight</span> - Disk Weight<span class="li-normal">type: str</span> <span class="li-required">required: false</span> <span class="li-normal">default: 100</span> </li>
    <li> <span class="li-head">domain_name</span> - The FQDN, such as www.example.com, to use in the DNS A/AAAA record health check.<span class="li-normal">type: str</span> <span class="li-required">required: false</span> </li>
    <li> <span class="li-head">down_retry</span> - Attempts to retry the health check to see if an up server has become unavailable.<span class="li-normal">type: str</span> <span class="li-required">required: false</span> </li>
    <li> <span class="li-head">file_name</span> - Specify a file that exists on the backend server. Path is relative to the initial login path. If the file does not exist or is not accessible, the health check fails.<span class="li-normal">type: str</span> <span class="li-required">required: false</span> <span class="li-normal">default: welcome.txt</span> </li>
    <li> <span class="li-head">folder_name</span> - Select an email mailbox to use in the health check. If the mailbox does not exist or is not accessible, the health check fails. The default is INBOX.<span class="li-normal">type: str</span> <span class="li-required">required: false</span> <span class="li-normal">default: INBOX</span> </li>
    <li> <span class="li-head">host_ip6_addr</span> - Specify the type IPv6 address used to inform a Diameter peer of the sender's IP address when the destination address type is IPv6. The default is blank, meaning that it is the address of the FortiADC's outgoing interface.<span class="li-normal">type: str</span> <span class="li-required">required: false</span> <span class="li-normal">default: ::</span> </li>
    <li> <span class="li-head">host_ip_addr</span> - Specify the type IPv4 address used to inform a Diameter peer of the sender's IP address when the destination address type is IPv4. The default is blank, meaning that it is the address of the FortiADC's outgoing interface.<span class="li-normal">type: str</span> <span class="li-required">required: false</span> <span class="li-normal">default: 0.0.0.0</span> </li>
    <li> <span class="li-head">hostname</span> - For HTTP or HTTPS health checks, you can specify the hostname (FQDN) instead of the destination IP address. This is useful in VM environments where multiple applications have the same IP address.<span class="li-normal">type: str</span> <span class="li-required">required: false</span> </li>
    <li> <span class="li-head">http_extra_string</span> - The non-empty additional string should end with '\r\n'.<span class="li-normal">type: str</span> <span class="li-required">required: false</span> </li>
    <li> <span class="li-head">host_addr</span> - IP address that matches the FQDN, indicating a successful health check.<span class="li-normal">type: str</span> <span class="li-required">required: false</span> <span class="li-normal">default: 0.0.0.0</span> </li>
    <li> <span class="li-head">host_addr6</span> - IP address that matches the FQDN, indicating a successful health check.<span class="li-normal">type: str</span> <span class="li-required">required: false</span> <span class="li-normal">default: ::</span> </li>
    <li> <span class="li-head">http_connect</span> - If the real server pool members are HTTP proxy servers, specify an HTTP CONNECT option.<span class="li-normal">type: str</span> <span class="li-required">required: false</span> <span class="li-normal">default:no_connect</span> </li>
    <li> <span class="li-head">http_version</span> - Specify the HTTP version<span class="li-normal">type: str</span> <span class="li-required">required: false</span> <span class="li-normal">default: http_1.1</span> </li>
    <li> <span class="li-head">interval</span> - Seconds between each health check. Should be more than the timeout to prevent overlapping health checks.<span class="li-normal">type: str</span> <span class="li-required">required: false</span> <span class="li-normal">default: 5</span> </li>
    <li> <span class="li-head">filter</span> - Criteria to use in selecting results.<span class="li-normal">type: str</span> <span class="li-required">required: false</span> </li>
    <li> <span class="li-head">local_cert</span> - Local SSL Health Check Client certificate.<span class="li-normal">type: str</span> <span class="li-required">required: false</span> <span class="li-normal">default: Factory</span> </li>
    <li> <span class="li-head">match_type</span> - Match String/Match Status/Match All (match both string and status)<span class="li-normal">type: str</span> <span class="li-required">required: false</span> <span class="li-normal">default: match_string</span> </li>
    <li> <span class="li-head">mem</span> - Maximum normal RAM usage. If overburdened, the health check fails.<span class="li-normal">type: str</span> <span class="li-required">required: false</span> <span class="li-normal">default: 96</span> </li>
    <li> <span class="li-head">mem_weight</span> - Memory weight<span class="li-normal">type: str</span> <span class="li-required">required: false</span> <span class="li-normal">default: 100</span> </li>
    <li> <span class="li-head">method_type</span> - HTTP method for the test traffic.<span class="li-normal">type: str</span> <span class="li-required">required: false</span> <span class="li-normal">default: http_head</span> </li>
    <li> <span class="li-head">mssql_row</span> - The row in which the send string (command) takes effect.<span class="li-normal">type: str</span> <span class="li-required">required: false</span> </li>
    <li> <span class="li-head">mssql_column</span> - The column in which the send string (command) takes effect.<span class="li-normal">type: str</span> <span class="li-required">required: false</span> </li>
    <li> <span class="li-head">mssql_receive_string</span> - A string expected in return when the request is successful.<span class="li-normal">type: str</span> <span class="li-required">required: false</span></li>
    <li> <span class="li-head">mssql_send_string</span> - The request string.<span class="li-normal">type: str</span> <span class="li-required">required: false</span> </li>
    <li> <span class="li-head">mysql_server_type</span> - MySQL server type (primary/secondary)<span class="li-normal">type: str</span> <span class="li-required">required: false</span> <span class="li-normal">default: primary</span> </li>
    <li> <span class="li-head">name</span> - Heath check name.<span class="li-normal">type: str</span> <span class="li-required">required: true</span> </li>
    <li> <span class="li-head">nas_ip</span> - NAS IP address RADIUS attribute (if the RADIUS server requires this attribute to make a connection).<span class="li-normal">type: str</span> <span class="li-required">required: false</span> </li>
    <li> <span class="li-head">oracle_receive_string</span> - The string we accept in order to receive.<span class="li-normal">type: str</span> <span class="li-required">required: false</span> </li>
    <li> <span class="li-head">oracle_send_string</span> - Send a string (command) to the OracleDb server.<span class="li-normal">type: str</span> <span class="li-required">required: false</span> </li>
    <li> <span class="li-head">origin_host</span> - Specify the FortiADC appliance that originates the Diameter message. The value is in FQDN format and used to uniquely identify a Diameter node for duplicate connection and routing loop detection.<span class="li-normal">type: str</span> <span class="li-required">required: false</span> </li>
    <li> <span class="li-head">origin_realm</span> - Specify the realm of the FortiADC appliance that originates the Diameter message. The value is in FQDN format.<span class="li-normal">type: str</span> <span class="li-required">required: false</span>  </li>
    <li> <span class="li-head">passive</span> - Select this option if the backend server uses passive FTP.<span class="li-normal">type: str</span> <span class="li-required">required: false</span> <span class="li-normal">default: enable</span> </li>
    <li> <span class="li-head">password</span> - Specify the password, if applicable.<span class="li-normal">type: str</span> <span class="li-required">required: false</span> </li>
    <li> <span class="li-head">pwd_type</span> - RADIUS password type (User/CHAP)<span class="li-normal">type: str</span> <span class="li-required">required: false</span> <span class="li-normal">default: user-password</span> </li>
    <li> <span class="li-head">port</span> - Specify the port number. Valid values range from 0 to 65535.<span class="li-normal">type: str</span> <span class="li-required">required: false</span> <span class="li-normal">default: 0</span> </li>
    <li> <span class="li-head">product_name</span> - Specify the type UTF8String product name which contains the vendor assigned name for the product.<span class="li-normal">type: str</span> <span class="li-required">required: false</span> <span class="li-normal">default: FortiADC</span> </li>
    <li> <span class="li-head">radius_reject</span> - RADIUS reject (enable/disable)<span class="li-normal">type: str</span> <span class="li-required">required: false</span> <span class="li-normal">default: disable</span> </li>
    <li> <span class="li-head">receive_string</span> - A string expected in return when the HTTP GET request is successful.<span class="li-normal">type: str</span> <span class="li-required">required: false</span> <span class="li-normal">default: receive-string</span> </li>
    <li> <span class="li-head">rtsp_method_type</span> - RTSP Options/RTSP Describe<span class="li-normal">type: str</span> <span class="li-required">required: false</span> <span class="li-normal">default: options</span> </li>
    <li> <span class="li-head">rtsp_describe_url</span> - Specify the RTSP describe URL<span class="li-normal">type: str</span> <span class="li-required">required: false</span> </li>
    <li> <span class="li-head">row</span> - The row in which the send string (command) takes effect<span class="li-normal">type: str</span> <span class="li-required">required: false</span> </li>
    <li> <span class="li-head">remote_username</span> - Remote server username.<span class="li-normal">type: str</span> <span class="li-required">required: false</span> </li>
    <li> <span class="li-head">remote_password</span> - Remote server password, if applicable.<span class="li-normal">type: str</span> <span class="li-required">required: false</span> </li>
    <li> <span class="li-head">remote_host</span> - If you use HTTP CONNECT to test proxy servers, specify the remote server IP address.<span class="li-normal">type: str</span> <span class="li-required">required: false</span> </li>
    <li> <span class="li-head">remote_port</span> - If you use HTTP CONNECT to test proxy servers, specify the remote server port.<span class="li-normal">type: str</span> <span class="li-required">required: false</span> <span class="li-normal">default: 0</span> </li>
    <li> <span class="li-head">script</span> - Specify the script which we create or which we have pre-defined<span class="li-normal">type: str</span> <span class="li-required">required: false</span> <span class="li-normal">default: CURL_HTTP_CODE</span> </li>
    <li> <span class="li-head">secret_key</span> - The secret set on the backend server.<span class="li-normal">type: str</span> <span class="li-required">required: false</span> </li>
    <li> <span class="li-head">send_string</span> - The request URL, such as /contact.php.<span class="li-normal">type: str</span> <span class="li-required">required: false</span> <span class="li-normal">default: /</span> </li>
    <li> <span class="li-head">sip_request_type</span> - Specify the SIP request type to be used for health checks: SIP Options/SIP Register<span class="li-normal">type: str</span> <span class="li-required">required: false</span> <span class="li-normal">default: register</span> </li>
    <li> <span class="li-head">ssl_ciphers</span> - List of SSL ciphers<span class="li-normal">type: str</span> <span class="li-required">required: false</span> <span class="li-normal">default: List</span> </li>
    <li> <span class="li-head">status_code</span> - The health check sends an HTTP request to the server. Specify the HTTP status code in the server reply that indicates a successful test. Typically, you use status code 200 (OK). Other status codes indicate errors.<span class="li-normal">type: str</span> <span class="li-required">required: false</span> <span class="li-normal">default: 200</span> </li>
    <li> <span class="li-head">timeout</span> - Seconds to wait for a reply before assuming that the health check has failed. The default is 5.<span class="li-normal">type: str</span> <span class="li-required">required: false</span> <span class="li-normal">default: 5</span> </li>
    <li> <span class="li-head">hc_type</span> - Health Check Type.<span class="li-normal">type: str</span> <span class="li-required">required: true</span> </li>
    <li> <span class="li-head">up_retry</span> - health check sends an HTTP request to the server. Specify the HTTP status code in the server reply that indicates a s Attempts to retry the health check to see if a down server has become available.<span class="li-normal">type: str</span> <span class="li-required">required: false</span> <span class="li-normal">default: 1</span> </li>
    <li> <span class="li-head">username</span> - Username of an account on the backend server.<span class="li-normal">type: str</span> <span class="li-required">required: false</span> </li>
    <li> <span class="li-head">vendor_id</span> - Specify the type Unsigned32 vendor ID which contains the IANA "SMI Network Management Private Enterprise Codes" value assigned to the vendor of a Diameter application.<span class="li-normal">type: str</span> <span class="li-required">required: false</span> <span class="li-normal">default: 12356</span> </li>
    <li> <span class="li-head">version</span> - SNMP v1 or v2c.<span class="li-normal">type: str</span> <span class="li-required">required: false</span> <span class="li-normal">default: v1</span> </li>
    <li> <span class="li-head">vdom</span> - VDOM name if enabled.<span class="li-normal">type: str</span> <span class="li-required">required: true (if VDOM is enabled)</span>  </li>
    </ul>


Examples
--------

.. code-block:: yaml+jinja

	- name:
	  hosts: all
	  connection: httpapi
	  gather_facts: false
	  tasks:
		- name: Manage Health Checks
		  fadcos_health_check:
			action: add
			name: test_hc
			dest_addr_type: ipv4
			dest_addr: 1.2.3.5
			up_retry: 1
			down_retry: 3
			interval: 5
			timeout: 3
			hc_type: icmp


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
