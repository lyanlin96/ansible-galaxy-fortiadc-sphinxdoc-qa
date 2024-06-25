:source: fadcos_system_setting.py

:orphan:

.. fadcos_system_setting:

fadcos_system_setting -- system setting configuration in Fortinet's FortiADC
++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++

.. versionadded:: 1.0.0

.. contents::
   :local:
   :depth: 1


Synopsis
--------
- Configure FortiADC system setting 



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
 <td>fortiadc_system_setting</td>
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
    <li> <span class="li-head">idle_timeout</span> - the idle time-out for system administration 1-480<span class="li-normal">type: str</span> <span class="li-required">required: false</span> <span class="li-normal">default: 30</span> </li>
    <li> <span class="li-head">config_sync</span> - config sync enable<span class="li-normal">type: str</span> <span class="li-required">required: false</span> <span class="li-normal">default: disable</span> </li>
    <li> <span class="li-head">intermediate_ca_group</span> - appliance's default ssl certificate chain<span class="li-normal">type: str</span> <span class="li-required">required: false</span> </li>
    <li> <span class="li-head">hostname</span> - appliance's host name<span class="li-normal">type: str</span> <span class="li-required">required: false</span> </li>
    <li> <span class="li-head">http_port</span> - the port number of the http service<span class="li-normal">type: str</span> <span class="li-required">required: false</span> </li>
    <li> <span class="li-head">https_port</span> - the port number of the https service<span class="li-normal">type: str</span> <span class="li-required">required: false</span></li>
    <li> <span class="li-head">https_server_cert</span> - appliance's local default certificate<span class="li-normal">type: str</span> <span class="li-required">required: false</span> </li>
    <li> <span class="li-head">ip_primary</span> - Primary DNS<span class="li-normal">type: str</span> <span class="li-required">required: false</span> </li>
    <li> <span class="li-head">ip_second</span> - Secondary DNS<span class="li-normal">type: str</span> <span class="li-required">required: false</span> </li>
    <li> <span class="li-head">ssh_port</span> - SSH port<span class="li-normal">type: str</span> <span class="li-required">required: false</span> </li>
    <li> <span class="li-head">sys_global_language</span> - Global GUI display language (english/chinese-simplified/japanese/spanish/chinese-traditional/portuguese)<span class="li-normal">type: str</span> <span class="li-required">required: false</span> </li>
    <li> <span class="li-head">telnet_port</span> - telnet port<span class="li-normal">type: str</span> <span class="li-required">required: false</span> </li>
    <li> <span class="li-head">vdom</span> - enable/disable vdom<span class="li-normal">type: str</span> <span class="li-required">required: false</span> </li>
    </ul>


Examples
--------

.. code-block:: yaml+jinja

	- name:
	  hosts: all
	  connection: httpapi
	  gather_facts: false
	  tasks:
		- name: Manage system setting
		  fadcos_system_setting:
		   idle_timeout: 78
		   config_sync: disable


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
