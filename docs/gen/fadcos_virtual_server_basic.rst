:source: fadcos_virtual_server_basic.py

:orphan:

.. fadcos_virtual_server_basic:

fadcos_virtual_server_basic -- virtual server basic configuration in Fortinet's FortiADC
++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++

.. versionadded:: 1.0.0

.. contents::
   :local:
   :depth: 1


Synopsis
--------
- Configure FortiADC virtual server basic



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
 <td>fortiadc_virtual_server_basic</td>
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
    <li> <span class="li-head">name</span> - virtual server name<span class="li-normal">type: str</span> <span class="li-required">required: true</span> </li>
    <li> <span class="li-head">application</span> - application type (ms-sharepoint/ms-exchange/smtp/http/http-turbo/http2-h2/http2-h2c/tcps/radius/dns/sip/rdp/rtmp/tcp/diameter/rtsp/udp/ftp/ip/iis/apache/iso8583/l7-tcp/l7-udp/)<span class="li-normal">type: str</span> <span class="li-required">required: true</span> </li>
    <li> <span class="li-head">address</span> - ip address of virtual server<span class="li-normal">type: str</span> <span class="li-required">required: true</span> </li>
    <li> <span class="li-head">interface</span> - interface name<span class="li-normal">type: str</span> <span class="li-required">required: true</span> </li>
    <li> <span class="li-head">pool</span> - pool name<span class="li-normal">type: str</span> <span class="li-required">required: true</span> </li>
    <li> <span class="li-head">port</span> - virtual server port<span class="li-normal">type: str</span> <span class="li-required">required: flase</span> <span class="li-normal">default: 80</span> </li>
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
		- name: Create basic virtual server
		  fadcos_virtual_server_basic:
		   name: test
		   application: http
		   address: 7.7.7.7
		   interface: port3
		   pool: rs_pool
		   port: 80


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
