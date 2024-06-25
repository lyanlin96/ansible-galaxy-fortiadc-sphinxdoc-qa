:source: fadcos_real_server_pool_member.py

:orphan:

.. fadcos_real_server_pool_member:

fadcos_real_server_pool_member -- real server pool member configuration in Fortinet's FortiADC
++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++

.. versionadded:: 1.0.0

.. contents::
   :local:
   :depth: 1


Synopsis
--------
- Configure FortiADC real server pool member



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
 <td>fortiadc_real_server_pool_member</td>
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
    <li> <span class="li-head">pool_name</span> - pool name<span class="li-normal">type: str</span> <span class="li-required">required: true</span> </li>
    <li> <span class="li-head">member_id</span> - pool member id<span class="li-normal">type: str</span> <span class="li-required">required: true</span> </li>
    <li> <span class="li-head">port</span> - pool member service port<span class="li-normal">type: str</span> <span class="li-required">required: false</span> <span class="li-normal">default: 80</span> </li>
    <li> <span class="li-head">rs</span> - real server<span class="li-normal">type: str</span> <span class="li-required">required: true</span> </li>
    <li> <span class="li-head">status</span> - (en|dis)able/maintain pool member<span class="li-normal">type: str</span> <span class="li-required">required: false</span> <span class="li-normal">default: enable</span> </li>
    <li> <span class="li-head">recover</span> - pool member recover time 0-86400<span class="li-normal">type: str</span> <span class="li-required">required: false</span> <span class="li-normal">default: 0</span> </li>
    <li> <span class="li-head">rs_profile_inherit</span> - real server SSL profile inherit(enable/disable)<span class="li-normal">type: str</span> <span class="li-required">required: false</span> <span class="li-normal">default: enable</span> </li>
    <li> <span class="li-head">rs_profile</span> - real server SSL profile name<span class="li-normal">type: str</span> <span class="li-required">required: true</span> </li>
    <li> <span class="li-head">warmrate</span> - pool member warm up rate 0-86400<span class="li-normal">type: str</span> <span class="li-required">required: false</span> <span class="li-normal">default: 100</span> </li>
    <li> <span class="li-head">weight</span> - pool member weight 1-256<span class="li-normal">type: str</span> <span class="li-required">required: false</span> <span class="li-normal">default: 1</span> </li>
    <li> <span class="li-head">warmup</span> - pool member warm up time 0-86400<span class="li-normal">type: str</span> <span class="li-required">required: false</span> <span class="li-normal">default: 0</span> </li>
    <li> <span class="li-head">backup</span> - set as backup server(enable/disable)<span class="li-normal">type: str</span> <span class="li-required">required: false</span> <span class="li-normal">default: disable</span> </li>
    <li> <span class="li-head">connlimit</span> - connection limit 0-1048576 <span class="li-normal">type: str</span> <span class="li-required">required: false</span> <span class="li-normal">default: 0</span> </li>
    <li> <span class="li-head">connection_ratelimit</span> - pool member connection rate limit(0 - 86400, disable), only work for L4VS<span class="li-normal">type: str</span> <span class="li-required">required: false</span> <span class="li-normal">default: 0</span> </li>
    <li> <span class="li-head">cookie</span> - pool member cookie<span class="li-normal">type: str</span> <span class="li-required">required: false</span> </li>
    <li> <span class="li-head">health_check_inherit</span> - health check inherit (enable/disable)<span class="li-normal">type: str</span> <span class="li-required">required: false</span> <span class="li-normal">default: enable</span> </li>
    <li> <span class="li-head">health_check</span> - health check control (enable/disable)<span class="li-normal">type: str</span> <span class="li-required">required: false</span> <span class="li-normal">default: disable</span> </li>
    <li> <span class="li-head">health_check_list</span> - health check list<span class="li-normal">type: str</span> <span class="li-required">required: true(if health_check enable)</span> </li>
    <li> <span class="li-head">health_check_relationship</span> - health check relationship (AND/OR)<span class="li-normal">type: str</span> <span class="li-required">required: false</span> <span class="li-normal">default: AND</span> </li>
    <li> <span class="li-head">mysql_group_id</span> - pool member mysql group id<span class="li-normal">type: str</span> <span class="li-required">required: false</span> <span class="li-normal">default: 0</span> </li>
    <li> <span class="li-head">mysql_read_only</span> - set as read only mysql server(enable/disable)<span class="li-normal">type: str</span> <span class="li-required">required: false</span> <span class="li-normal">default: disable</span> </li>
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
		- name: Manage real server pool member
		  fadcos_real_server_pool_member:
			action: delete
			pool_name: rs_pool
			member_id: 3
			rs: 999


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
