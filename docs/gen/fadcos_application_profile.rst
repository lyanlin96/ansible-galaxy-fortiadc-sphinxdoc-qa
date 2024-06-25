:source: fadcos_application_profile.py

:orphan:

.. fadcos_application_profile:

fadcos_application_profile -- application profile configuration in Fortinet's FortiADC
++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++

.. versionadded:: 1.0.0

.. contents::
   :local:
   :depth: 1


Synopsis
--------
- Configure FortiADC application profile



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
 <td>fortiadc_application_profile</td>
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
    <li> <span class="li-head">action</span> - Type of action to perform on the object. <span class="li-normal">type: str</span> <span class="li-required">required: true</span> </li>
    <li> <span class="li-head">name</span> - Application profile name. <span class="li-normal">type: str</span> <span class="li-required">required: true</span> </li>
    <li> <span class="li-head">type</span> - Application profile type. <span class="li-normal">type: str</span> <span class="li-required">required: true</span> </li>
    <li> <span class="li-head">timeout_tcp_session</span> - Client-side timeout for connections where the client has not sent a FIN signal, but the connection has been idle. The default is 100 seconds. The valid range is 1 to 86,400. <span class="li-normal">type: str</span> <span class="li-required">required: false</span> <span class="li-normal">default: 100</span> </li>
    <li> <span class="li-head">timeout_tcp_session_after_fin</span> - Client-side connection timeout. The default is 100 seconds. The valid range is 1 to 86,400. <span class="li-normal">type: str</span> <span class="li-required">required: false</span> <span class="li-normal">default: 100</span> </li>
    <li> <span class="li-head">ip_reputation</span> - Enable to apply FortiGuard IP reputation service.<span class="li-normal">type: str</span> <span class="li-required">required: false</span> <span class="li-normal">default: disable</span> </li>
    <li> <span class="li-head">ip_reputation_redirect</span> - Type a URL including the FQDN/IP and path, if any, to which a client will be redirected if the request violates the IP reputation policy.<span class="li-normal">type: str</span> <span class="li-required">required: false</span> <span class="li-normal">default: http://</span> </li>
    <li> <span class="li-head">stateless</span> - Enable to apply UDP stateless function.<span class="li-normal">type: str</span> <span class="li-required">required: false</span> <span class="li-normal">default: disable</span> </li>
    <li> <span class="li-head">timeout_udp_session</span> - Client-side session timeout. The default is 100 seconds. The valid range is 1 to 86,400.<span class="li-normal">type: str</span> <span class="li-required">required: false</span> <span class="li-normal">default: 100</span> </li>
    <li> <span class="li-head">client_timeout</span> - This timeout is counted as the amount of time when the client did not send a complete request HTTP header to the FortiADC after the client connected to the FortiADC. If this timeout expires, FortiADC will send a 408 message to client and close the connection to the client.<span class="li-normal">type: str</span> <span class="li-required">required: false</span> <span class="li-normal">default: 50</span> </li>
    <li> <span class="li-head">server_timeout</span> - This timeout is counted as the amount of time when the server did not send a complete response HTTP header to the FortiADC after the FortiADC sent a request to server. If this timeout expires, FortiADC will close the server side connection and send a 503 message to the client and close the connection to the client.<span class="li-normal">type: str</span> <span class="li-required">required: false</span> <span class="li-normal">default: 50</span> </li>
    <li> <span class="li-head">connect_timeout</span> - This timeout is counted as the amount of time during which FortiADC tried to connect to the server with TCP SYN. After this timeout, if TCP connection is not established, FortiADC will drop this current connection to server and respond with a 503 message to client side and close the connection to the client.<span class="li-normal">type: str</span> <span class="li-required">required: false</span> <span class="li-normal">default: 5</span> </li>
    <li> <span class="li-head">queue_timeout</span> - This timeout is counted as the amount of time during which the request is queued in the dispatched queue. When the request cannot be dispatched to a server by a load balance method (for example, the server's connection limited is reached), it will be put into a queue. If this timeout expires, the request in the queue will be dropped and FortiADC will respond with a 503 message to client side and close the connection to the client.<span class="li-normal">type: str</span> <span class="li-required">required: false</span> <span class="li-normal">default: 5</span> </li>
    <li> <span class="li-head">http_send_timeout</span> - This timeout is counted as the amount of time it took FortiADC to send a response body data (not including the header); the time is counted starting from when the body is transferred. If this timeout expires, FortiADC will close the connection of both side.<span class="li-normal">type: str</span> <span class="li-required">required: false</span> <span class="li-normal">default: 0</span> </li>
    <li> <span class="li-head">http_request_timeout</span> - This timeout is counted as the amount of time the client did not send a complete request (including both HTTP header and request body) to FortiADC after the client connected to FortiADC. If this timeout expires, FortiADC will send a 408 message to client and close the connection to the client.<span class="li-normal">type: str</span> <span class="li-required">required: false</span> <span class="li-normal">default: 50</span> </li>
    <li> <span class="li-head">http_keepalive_timeout</span> - This timeout is counted as the time FortiADC can wait for a new request after the previous transaction is completed. This is an idle timeout if the client does not send anything in this period. If this timeout expires, FortiADC will close the connection to the client.<span class="li-normal">type: str</span> <span class="li-required">required: false</span> <span class="li-normal">default: 50</span> </li>
    <li> <span class="li-head">client_address</span> - Use the original client IP address as the source address when connecting to the real server.<span class="li-normal">type: str</span> <span class="li-required">required: false</span> </li>
    <li> <span class="li-head">http_x_forwarded_for</span> - Enable this option to append the client IP address found in IP layer packets to the HTTP header.<span class="li-normal">type: str</span> <span class="li-required">required: false</span> <span class="li-normal">default: disable</span> </li>
    <li> <span class="li-head">http_x_forwarded_for_header</span> - Specify a custom name for the HTTP header which carries the client IP address.<span class="li-normal">type: str</span> <span class="li-required">required: false</span></li>
    <li> <span class="li-head">http_mode</span> - HTTP mode. (serverclose/onceonly/KeepAlive)<span class="li-normal">type: str</span> <span class="li-required">required: false</span> <span class="li-normal">default: KeepAlive</span> </li>
    <li> <span class="li-head">security_mode</span> - Security Mode (none/explicit/implicit)<span class="li-normal">type: str</span> <span class="li-required">required: false</span> <span class="li-normal">default: none</span> </li>
    <li> <span class="li-head">timeout_ip_session</span> - Client-side session timeout. The default is 100 seconds. The valid range is 1 to 86,400.<span class="li-normal">type: str</span> <span class="li-required">required: false</span> <span class="li-normal">default: 100</span> </li>
    <li> <span class="li-head">timeout_radius_session</span> - The default is 300 seconds. The valid range is 1 to 3,600.<span class="li-normal">type: str</span> <span class="li-required">required: false</span> <span class="li-normal">default: 300</span> </li>
    <li> <span class="li-head">source_port</span> - Use the original client port as the source port when connecting to the real server.<span class="li-normal">type: str</span> <span class="li-required">required: false</span></li>
    <li> <span class="li-head">dynamic_auth</span> - Enable or disable Dynamic Authorization for RADIUS Change of Authorization(CoA)<span class="li-normal">type: str</span> <span class="li-required">required: false</span> <span class="li-normal">default: disable</span> </li>
    <li> <span class="li-head">dynamic_auth_port</span> - Configures the UDP port for CoA requests. The default is 3799.<span class="li-normal">type: str</span> <span class="li-required">required: false</span> <span class="li-normal">default: 3799</span> </li>
    <li> <span class="li-head">max_header_size</span> - Specify the maximum size of the RTSP header.<span class="li-normal">type: str</span> <span class="li-required">required: false</span> <span class="li-normal">default: 4096</span> </li>
    <li> <span class="li-head">max_http_headers</span> - Adjust the max header number that HTTP/HTTPS VS can process for every request or response. If a request or response has a header over this limit, it will be dropped, and error message 400 will be returned.<span class="li-normal">type: str</span> <span class="li-required">required: false</span> <span class="li-normal">default: 100</span> </li>
    <li> <span class="li-head">tune_bufsize</span> - Adjust the value of the HTTP/HTTPS VS's connection buffer size.<span class="li-normal">type: str</span> <span class="li-required">required: false</span> <span class="li-normal">default: 8030</span> </li>
    <li> <span class="li-head">response_half_closed_request</span> - Continue to response to the half-closed connections.<span class="li-normal">type: str</span> <span class="li-required">required: false</span> <span class="li-normal">default: disable</span> </li>
    <li> <span class="li-head">vdom</span> - VDOM name if enabled.<span class="li-normal">type: str</span> <span class="li-required">required: true (if VDOM is enabled)</span> <span class="li-normal">default: N/A</span> </li>
    </ul>


Examples
--------

.. code-block:: yaml+jinja

	- name:
	  hosts: all
	  connection: httpapi
	  gather_facts: false
	  tasks:
		- name: Manage Application Profile
		  fadcos_application_profile:
			action: add
			name: ansible_test_1
			type: tcp
			timeout_tcp_session: 150
			ip_reputation: disable
    


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
