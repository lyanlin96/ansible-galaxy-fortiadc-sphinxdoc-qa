:source: fadcos_system_vdom.py

:orphan:

.. fadcos_system_vdom:

fadcos_system_vdom -- Configure the parameters of each VDOM in Fortinet's FortiADC
++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++

.. versionadded:: 1.1.0

.. contents::
   :local:
   :depth: 1


Synopsis
--------
- Configure the parameters of each VDOM in Virtual Domain Page 



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
 <td><code class="docutils literal notranslate">v7.1.4 </code></td>
 <td><code class="docutils literal notranslate">v7.2.2 </code></td>
 <td><code class="docutils literal notranslate">v7.4.0 </code></td>
 </tr>
 <tr>
 <td>fadcos_system_vdom</td>
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
    <li> <span class="li-head">name</span> - Specify the vdom name <span class="li-normal">type: str</span> <span class="li-required">required: true</span> </li>
    <li> <span class="li-head">l4cps</span> - The number of layer 4 connections created per second. (0-1000000)<span class="li-normal">type: str</span> <span class="li-required">required: false</span> <span class="li-normal">default: 0</span></li>
    <li> <span class="li-head">l7cps</span> - The number of layer 7 TCP connections created by the httproxy frontend per second. (0-1000000)<span class="li-normal">type: str</span> <span class="li-required">required: false</span> <span class="li-normal">default: 0</span></li>
    <li> <span class="li-head">l7rps</span> - The number of HTTP GET requests handled by the httproxy from the client side per second. (0-1000000)<span class="li-normal">type: str</span> <span class="li-required">required: false</span> <span class="li-normal">default: 0</span></li>
    <li> <span class="li-head">sslcps</span> - The number of SSL connections created by the httproxy frontend per second. (0-1000000)<span class="li-normal">type: str</span> <span class="li-required">required: false</span> <span class="li-normal">default: 0</span></li>
    <li> <span class="li-head">sslthroughput</span> - The volume of SSL encrypted TCP traffic from both the incoming and outgoing side. (0-10000000 Kbps)<span class="li-normal">type: str</span> <span class="li-required">required: false</span> <span class="li-normal">default: 0</span></li>
    <li> <span class="li-head">concurrentsession</span> - The total number of living connections for ADC traffic. (0-1000000)<span class="li-normal">type: str</span> <span class="li-required">required: false</span> <span class="li-normal">default: 0</span></li>
    <li> <span class="li-head">inbound</span> - The maximum volume of inbound traffic allowed. (0-40000000 Kbps)<span class="li-normal">type: str</span> <span class="li-required">required: false</span> <span class="li-normal">default: 0</span></li>
    <li> <span class="li-head">outbound</span> - The maximum volume of outbound traffic allowed. (0-40000000 Kbps)<span class="li-normal">type: str</span> <span class="li-required">required: false</span> <span class="li-normal">default: 0</span></li>
    <li> <span class="li-head">virtual_server</span> - The maximum number of virtual servers. (0-1024)<span class="li-normal">type: str</span> <span class="li-required">required: false</span> <span class="li-normal">default: 0</span></li>
    <li> <span class="li-head">real_server</span> - The maximum number of real servers. (0-1024)<span class="li-normal">type: str</span> <span class="li-required">required: false</span> <span class="li-normal">default: 0</span></li>
    <li> <span class="li-head">health_check</span> - The maximum number of healthcheck members. (0-1024)<span class="li-normal">type: str</span> <span class="li-required">required: false</span> <span class="li-normal">default: 0</span></li>
    <li> <span class="li-head">source_pool</span> - The maximum number of IP pools. (0-1024)<span class="li-normal">type: str</span> <span class="li-required">required: false</span> <span class="li-normal">default: 0</span></li>
    <li> <span class="li-head">error_page</span> - The maximum number of error page files. (0-1024)<span class="li-normal">type: str</span> <span class="li-required">required: false</span> <span class="li-normal">default: 0</span></li>
    <li> <span class="li-head">local_user</span> - The maximum number of local users. (0-1024)<span class="li-normal">type: str</span> <span class="li-required">required: false</span> <span class="li-normal">default: 0</span></li>
    <li> <span class="li-head">user_group</span> - The maximum number of user groups. (0-1024)<span class="li-normal">type: str</span> <span class="li-required">required: false</span> <span class="li-normal">default: 0</span></li>
    </ul>


Examples
--------

.. code-block:: yaml+jinja

        - name:
          hosts: all
          vars:
          connection: httpapi
          gather_facts: false
          tasks:
            - name: edit
              fadcos_system_vdom:
               action: edit
               name: vd1
               l4cps: 1
               l7cps: 1
               l7rps: 1
               sslcps: 1
               sslthroughput: 1
               concurrentsession: 1
               inbound: 1
               outbound: 1
               virtual_server: 1
               real_server: 1
               health_check: 4
               source_pool: 1
               error_page: 1
               local_user: 1
               user_group: 1

            - name: get
              fadcos_system_vdom:
               action: get
               name: vd1

    
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

- Wayne Chou


.. hint::
    If you notice any issues in this documentation, you can create a pull request to improve it.
