:source: fadcos_local_cert_group.py

:orphan:

.. fadcos_local_cert_group:

fadcos_local_cert_group -- local cert group configuration in Fortinet's FortiADC
++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++

.. versionadded:: 1.0.0

.. contents::
   :local:
   :depth: 1


Synopsis
--------
- Configure FortiADC local cert group



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
 <td>fortiadc_local_cert_group</td>
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
    <li> <span class="li-head">name</span> - Local certificate group name.<span class="li-normal">type: str</span> <span class="li-required">required: true</span> </li>
    <li> <span class="li-head">member_id</span> - Local certificate group member ID.<span class="li-normal">type: str</span> <span class="li-required">required: true</span> </li>
    <li> <span class="li-head">OCSP_stapling</span> - Select an OCSP Stapling configuration. The local certificate in the OCSP Stapling configuration must match the local certificate in the local certificate group member.<span class="li-normal">type: str</span> <span class="li-required">required: false</span> </li>
    <li> <span class="li-head">default</span> - Enable if you want to make this local certificate the default for the group.<span class="li-normal">type: str</span> <span class="li-required">required: false</span> <span class="li-normal">default: disable</span> </li>
    <li> <span class="li-head">extra_local_cert</span> - FortiADC supports dual SSL certificates, one for an RSA-based SSL certificate and the other for an ECDSA-based SSL certificate. This option allows you to add an additional local certificate along with an additional OCSP stapling and intermediate CA group to a local certificate group configuration.<span class="li-normal">type: str</span> <span class="li-required">required: false</span> </li>
    <li> <span class="li-head">intermediate_cag</span> - Select an intermediate CA group to add to the local group.<span class="li-normal">type: str</span> <span class="li-required">required: false</span> </li>
    <li> <span class="li-head">local_cert</span> - Select a local certificate to add to the group.<span class="li-normal">type: str</span> <span class="li-required">required: false</span> <span class="li-normal">default: Factory</span> </li>
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
		- name: Manage Local Certificate Group
		  fadcos_local_cert_group:
			action: add_group
			name: ansible_test_G2
		- name: Manage Local Certificate Group Members
		  fadcos_local_cert_group:
			action: add_member
			name: ansible_test_G2


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
