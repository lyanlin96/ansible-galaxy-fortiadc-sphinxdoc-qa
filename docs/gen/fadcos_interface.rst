:source: fadcos_interface.py

:orphan:

.. fadcos_interface:

fadcos_interface -- interface configuration in Fortinet's FortiADC
++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++

.. versionadded:: 1.0.0

.. contents::
   :local:
   :depth: 1


Synopsis
--------
- Configure FortiADC interface



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
 <td>fortiadc_interface</td>
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
    <li> <span class="li-head">name</span> - interface name<span class="li-normal">type: str</span> <span class="li-required">required: true</span> </li>
    <li> <span class="li-head">mode</span> - static,pppoe or dhcp<span class="li-normal">type: str</span> <span class="li-required">required: false</span> <span class="li-normal">default: static</span> </li>
    <li> <span class="li-head">status</span> - interface status up/down<span class="li-normal">type: str</span> <span class="li-required">required: false</span> <span class="li-normal">default: up</span> </li>
    <li> <span class="li-head">IPandMask</span> - ip address of interface<span class="li-normal">type: str</span> <span class="li-required">required: true (if mode is static and IPv6andMask not set)</span> </li>
    <li> <span class="li-head">IPv6andMask</span> - ipv6 address of interface<span class="li-normal">type: str</span> <span class="li-required">required: true (if mode is static and IPandMask not set)</span> </li>
    <li> <span class="li-head">allowaccess</span> - Allow access with the interfacei(https, ping, ssh, snmp, http, telnet)<span class="li-normal">type: str</span> <span class="li-required">required: false</span> </li>
    <li> <span class="li-head">intf_type</span> - interface type(physical/vlan/aggregate/loopback/soft-switch/vxlan/nvgre/vdom-link)<span class="li-normal">type: str</span> <span class="li-required">required: true</span></li>
    <li> <span class="li-head">vlanid</span> - Vlan ID<span class="li-normal">type: str</span> <span class="li-required">required: true (if type is vlan)</span></li>
    <li> <span class="li-head">vdom</span> - vdom name<span class="li-normal">type: str</span> <span class="li-required">required: true (if VDOM is enabled) </span> </li>
    <li> <span class="li-head">interface</span> - physical interface name<span class="li-normal">type: str</span> <span class="li-required">required: true (if intf_type is vlan)</span> </li>
    <li> <span class="li-head">mtu</span> - maximum transportation unit 68-9000<span class="li-normal">type: str</span> <span class="li-required">required: false</span> <span class="li-normal">default: 1500</span> </li>
    <li> <span class="li-head">aggregate_algorithm</span> - aggregate interface slave selection algorithm layer2/layer2-3/layer3-4<span class="li-normal">type: str</span> <span class="li-required">required: false</span> <span class="li-normal">default: layer2-3</span> </li>
    <li> <span class="li-head">aggregate_mode</span> - aggregate mode (balance-rr/balance-xor/broadcast/802.3ad/balance-tlb/balance-alb)<span class="li-normal">type: str</span> <span class="li-required">required: false</span> <span class="li-normal">default: 802.3ad</span> </li>
    <li> <span class="li-head">default_gw</span> - default gateway<span class="li-normal">type: str</span> <span class="li-required">required: false</span> </li>
    <li> <span class="li-head">dhcp_gw_override</span> - enable/disable to override gateway<span class="li-normal">type: str</span> <span class="li-required">required: false</span> <span class="li-normal">default: disable</span> </li>
    <li> <span class="li-head">dhcp_gw_distance</span> - distance for dhcp_gateway<span class="li-normal">type: str</span> <span class="li-required">required: false</span> <span class="li-normal">default: 10</span> </li>
    <li> <span class="li-head">disc_retry_timeout</span> - pppoe discovery retry timeout<span class="li-normal">type: str</span> <span class="li-required">required: false</span> <span class="li-normal">default: 5</span> </li>
    <li> <span class="li-head">pppoe_username</span> - pppoe account user name<span class="li-normal">type: str</span> <span class="li-required">required: false</span> </li>
    <li> <span class="li-head">pppoe_passwd</span> - pppoe account password<span class="li-normal">type: str</span> <span class="li-required">required: false</span> <span class="li-normal">default: </span> </li>
    <li> <span class="li-head">floating</span> - enable/disable to set floating ip<span class="li-normal">type: str</span> <span class="li-required">required: false</span> <span class="li-normal">default: disable</span> </li>
    <li> <span class="li-head">floating_ip</span> - floating ip address of interface<span class="li-normal">type: str</span> <span class="li-required">required: false</span> <span class="li-normal">default: 0.0.0.0</span> </li>
    <li> <span class="li-head">redundant_member</span> - redundant/aggregate interface slaves<span class="li-normal">type: str</span> <span class="li-required">required: false</span> </li>
    <li> <span class="li-head">traffic_group</span> - traffic group name<span class="li-normal">type: str</span> <span class="li-required">required: false</span> </li>
    </ul>


Examples
--------

.. code-block:: yaml+jinja

	- name:
	  hosts: all
	  connection: httpapi
	  gather_facts: false
	  tasks:
		- name: Manage interface
		  fadcos_interface:
		   action: get
		   name: testport
		   mode: static
		   intf_type: vlan
		   interface: port5
		   vlanid: 100
		   IPandMask: 123.23.3.12/24
		   allowaccess:
				   - snmp
				   - http


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
