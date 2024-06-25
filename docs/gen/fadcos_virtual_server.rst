:source: fadcos_virtual_server.py

:orphan:

.. fadcos_virtual_server:

fadcos_virtual_server -- virtual server configuration in Fortinet's FortiADC
++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++

.. versionadded:: 1.0.0

.. contents::
   :local:
   :depth: 1


Synopsis
--------
- Configure FortiADC virtual server



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
 <td>fortiadc_virtual_server</td>
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
    <li> <span class="li-head">name</span> - virtual-server name<span class="li-normal">type: str</span> <span class="li-required">required: true</span> </li>
    <li> <span class="li-head">status</span> - enable/maintain/disable virtual server<span class="li-normal">type: str</span> <span class="li-required">required: true</span> </li>
    <li> <span class="li-head">iptype</span> - address type ipv4/ipv6<span class="li-normal">type: str</span> <span class="li-required">required: false</span> <span class="li-normal">default: ipv4</span> </li>
    <li> <span class="li-head">ip</span> - ip address of virtual server<span class="li-normal">type: str</span> <span class="li-required">required: true</span> </li>
    <li> <span class="li-head">public_iptype</span> - address type ipv4/ipv6<span class="li-normal">type: str</span> <span class="li-required">required: false</span> <span class="li-normal">default: ipv4</span> </li>
    <li> <span class="li-head">public_ip</span> - public ip address of virtual server<span class="li-normal">type: str</span> <span class="li-required">required: false</span> <span class="li-normal">default: 0.0.0.0</span> </li>
    <li> <span class="li-head">interface</span> - interface name<span class="li-normal">type: str</span> <span class="li-required">required: true</span></li>
    <li> <span class="li-head">vstype</span> - virtual-server service type l4-load-balance/l7-load-balance/l2-load-balance<span class="li-normal">type: str</span> <span class="li-required">required: false</span> <span class="li-normal">default: l4-load-balance</span> </li>
    <li> <span class="li-head">pool</span> - ip pool name<span class="li-normal">type: str</span> <span class="li-required">required: true</span> </li>
    <li> <span class="li-head">port</span> - virtual server service port 1-65535<span class="li-normal">type: str</span> <span class="li-required">required: false</span> <span class="li-normal">default: 80</span> </li>
    <li> <span class="li-head">profile</span> - profile name<span class="li-normal">type: str</span> <span class="li-required">required: true</span></li>
    <li> <span class="li-head">method</span> - "method name<span class="li-normal">type: str</span> <span class="li-required">required: false</span> <span class="li-normal">default: LB_METHOD_ROUND_ROBIN</span></li>
    <li> <span class="li-head">ssl_mirror</span> - enable/disable SSL mirror<span class="li-normal">type: str</span> <span class="li-required">required: false</span> <span class="li-normal">default: disable</span> </li>
    <li> <span class="li-head">ssl_mirror_intf</span> - interface list to mirror<span class="li-normal">type: str</span> <span class="li-required">required: true (if ssl_mirror is enable)</span> </li>
    <li> <span class="li-head">traffic_group</span> - traffic group name <span class="li-normal">type: str</span> <span class="li-required">required: false</span> </li>
    <li> <span class="li-head">traffic_log</span> - enable/disable traffic log<span class="li-normal">type: str</span> <span class="li-required">required: false</span> <span class="li-normal">default: disable</span> </li>
    <li> <span class="li-head">trans_rate_limit</span> - virtual server transactions rate limit<span class="li-normal">type: str</span> <span class="li-required">required: false</span> <span class="li-normal">default: 0</span> </li>
    <li> <span class="li-head">warmrate</span> - virtual server warm up rate 1-86400<span class="li-normal">type: str</span> <span class="li-required">required: false</span> <span class="li-normal">default: 100</span> </li>
    <li> <span class="li-head">warmup</span> - virtual server warm up time 0-86400<span class="li-normal">type: str</span> <span class="li-required">required: false</span> <span class="li-normal">default: 0</span> </li>
    <li> <span class="li-head">alone</span> - enable/disable alone mode<span class="li-normal">type: str</span> <span class="li-required">required: false</span> <span class="li-normal">default: enable</span> </li>
    <li> <span class="li-head">av_profile</span> - antivirus profile name<span class="li-normal">type: str</span> <span class="li-required">required: false</span></li>
    <li> <span class="li-head">client_ssl_profile</span> - client SSL profile<span class="li-normal">type: str</span> <span class="li-required">required: true</span></li>
    <li> <span class="li-head">clone_pool</span> - clone pool name<span class="li-normal">type: str</span> <span class="li-required">required: false</span> <span class="li-normal">default: </span> </li>
    <li> <span class="li-head">clone_traffic_type</span> - the traffic type to be cloned both-sides/client-side/server-side<span class="li-normal">type: str</span> <span class="li-required">required: false</span> <span class="li-normal">default: both-sides</span> </li>
    <li> <span class="li-head">connection_rate_limit</span> - virtual server connection rate limit(0 - disable) 0-86400<span class="li-normal">type: str</span> <span class="li-required">required: false</span> <span class="li-normal">default: 0</span> </li>
    <li> <span class="li-head">connection_limit</span> - connection-limit 0-100000000<span class="li-normal">type: str</span> <span class="li-required">required: false</span> <span class="li-normal">default: 0</span> </li>
    <li> <span class="li-head">content_rewriting</span> - content rewriting<span class="li-normal">type: str</span> <span class="li-required">required: false</span> <span class="li-normal">default: disable</span> </li>
    <li> <span class="li-head">content_rewriting_list</span> - content rewriting list<span class="li-normal">type: list</span> <span class="li-required">required: true (if content rewriting is enable)</span> </li>
    <li> <span class="li-head">content_routing</span> - content routing<span class="li-normal">type: str</span> <span class="li-required">required: false</span> <span class="li-normal">default: disable</span> </li>
    <li> <span class="li-head">content_routing_list</span> - content routing list<span class="li-normal">type: list</span> <span class="li-required">required: true (if content routing is enable)</span></li>
    <li> <span class="li-head">schedule_list</span> - enable/disable schedule list<span class="li-normal">type: list</span> <span class="li-required">required: false</span> <span class="li-normal">default: disable</span> </li>
    <li> <span class="li-head">schedule_pool_list</span> - schedule pool name<span class="li-normal">type: list</span> <span class="li-required">required: false</span> </li>
    <li> <span class="li-head">scripting_flag</span> - enable/disable virtual server scripting<span class="li-normal">type: str</span> <span class="li-required">required: false</span> <span class="li-normal">default: disable</span> </li>
    <li> <span class="li-head">scripting_list</span> - virtual server scripting list<span class="li-normal">type: str</span> <span class="li-required">required: true (if scripting_flag is enable)</span> </li>
    <li> <span class="li-head">source_pool_list</span> - ip pool name<span class="li-normal">type: list</span> <span class="li-required">required: false</span> </li>
    <li> <span class="li-head">waf_profile</span> - web application firewall profile name<span class="li-normal">type: str</span> <span class="li-required">required: false</span> </li>
    <li> <span class="li-head">http2https</span> - enable/disable redirect HTTP request to HTTPS<span class="li-normal">type: str</span> <span class="li-required">required: false</span> <span class="li-normal">default: disable</span> </li>
    <li> <span class="li-head">http2https_port</span> - HTTP service port list for redirecting HTTP to HTTPS<span class="li-normal">type: str</span> <span class="li-required">required: false</span> <span class="li-normal">default: 80</span> </li>
    <li> <span class="li-head">l2_exception_list</span> - layer2 exception list<span class="li-normal">type: str</span> <span class="li-required">required: false</span> </li>
    <li> <span class="li-head">packet_fwd_method</span> - packet forwarding method direct_routing/NAT/FullNAT/NAT46/NAT64/tunneling<span class="li-normal">type: str</span> <span class="li-required">required: false</span> <span class="li-normal">default: NAT</span> </li>
    <li> <span class="li-head">pagespeed</span> - virtual server pagespeed<span class="li-normal">type: str</span> <span class="li-required">required: false</span> </li>
    <li> <span class="li-head">persistence</span> - persistence name<span class="li-normal">type: str</span> <span class="li-required">required: false</span> </li>
    <li> <span class="li-head">protocol</span> - "virtual server protocol numbers<span class="li-normal">type: str</span> <span class="li-required">required: false</span> <span class="li-normal">default: 0</span> </li>
    <li> <span class="li-head">adfs_published_service</span> - AD FS published service<span class="li-normal">type: str</span> <span class="li-required">required: false</span> </li>
    <li> <span class="li-head">error_msg</span> - error message<span class="li-normal">type: str</span> <span class="li-required">required: false</span> <span class="li-normal">default: Server-unavailable!</span> </li>
    <li> <span class="li-head">error_page</span> - error-page name<span class="li-normal">type: str</span> <span class="li-required">required: false</span> </li>
    <li> <span class="li-head">fortiview</span> - enable/disable fortiview<span class="li-normal">type: str</span> <span class="li-required">required: false</span> <span class="li-normal">default: disable</span> </li>
    <li> <span class="li-head">wccp</span> - enable/disable redirect HTTP/HTTPS request to WCCP client<span class="li-normal">type: str</span> <span class="li-required">required: false</span> <span class="li-normal">default: disable</span> </li>
    <li> <span class="li-head">comments</span> - virtual server comments<span class="li-normal">type: str</span> <span class="li-required">required: false</span> <span class="li-normal">default: ""</span> </li>
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
		- name: Manage virtual server
		  fadcos_virtual_server:
		   action: edit
		   name: test
		   status: enable
		   iptype: ipv4
		   ip: 7.7.7.1
		   interface: port3
		   pool: rs_pool
		   port: 80
		   profile: LB_PROF_TCP
		   vstype: l4-load-balance


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
