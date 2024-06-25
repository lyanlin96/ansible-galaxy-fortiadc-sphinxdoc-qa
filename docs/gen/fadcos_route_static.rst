:source: fadcos_route_static.py

:orphan:

.. fadcos_route_static:

fadcos_route_static -- route static configuration in Fortinet's FortiADC
++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++

.. versionadded:: 1.0.0

.. contents::
   :local:
   :depth: 1


Synopsis
--------
- Configure FortiADC route static



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
 <td>fortiadc_route_static</td>
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
    <li> <span class="li-head">route_id</span> - The number of the route<span class="li-normal">type: str</span> <span class="li-required">required: true</span> </li>
    <li> <span class="li-head">desination</span> - Destination for this route<span class="li-normal">type: str</span> <span class="li-required">required: true</span> </li>
    <li> <span class="li-head">gateway</span> - Gateway for this route<span class="li-normal">type: str</span> <span class="li-required">required: true</span> </li>
    <li> <span class="li-head">distance</span> - distance for this route<span class="li-normal">type: str</span> <span class="li-required">required: false</span> <span class="li-normal">default: 10</span> </li>
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
		- name: Manage route satatic
		  fadcos_route_static:
		   action: add
		   route_id: 2
		   desination: 66.1.1.0/24
		   gateway: 66.1.1.254
		   distance: 10
		   vdom: root

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
