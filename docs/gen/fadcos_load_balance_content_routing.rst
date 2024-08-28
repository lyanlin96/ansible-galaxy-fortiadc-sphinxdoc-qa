:source: fadcos_load_balance_content_routing.py

:orphan:

.. fadcos_load_balance_content_routing:

fadcos_load_balance_content_routing -- configure content routing in Fortinet's FortiADC
++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++

.. versionadded:: 1.1.0

.. contents::
   :local:
   :depth: 1


Synopsis
--------
- Configure Content Routing on Virtual Server in Server Load Balance Page 



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
 <td>fadcos_load_balance_content_routing</td>
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
    <li> <span class="li-head">name</span> - config name <span class="li-normal">type: str</span> <span class="li-required">required: false</span> </li>
    <li> <span class="li-head">connection_pool_inherit</span> - enable to use the connection pool configuration object specified in the virtual server configuration.<span class="li-normal">type: str</span> <span class="li-required">required: false</span> <span class="li-normal">default: enable</span> </li>
    <li> <span class="li-head">type</span> - Layer 4 or Layer 7 content routing.<span class="li-normal">type: str</span> <span class="li-required">required: false</span> <span class="li-normal">default: l4-content-routing</span></li>
    <li> <span class="li-head">ip</span> - Address/mask notation to match the source IP address in the packet header.<span class="li-normal">type: str</span> <span class="li-required">required: false</span> <span class="li-normal">default: 0.0.0.0/0</span> </li>
    <li> <span class="li-head">ip6</span> - Address/mask notation to match the source IP address in the packet header.<span class="li-normal">type: str</span> <span class="li-required">required: false</span> <span class="li-normal">default: ::/0</span> </li>
    <li> <span class="li-head">pool</span> - Specify Real Server Pool.<span class="li-normal">type: str</span> <span class="li-required">required: false</span> <span class="li-normal">default: rs_pool</span> </li>
    <li> <span class="li-head">method_inherit</span> - Enable (default) to use the method specified in the virtual server configuration.<span class="li-normal">type: str</span> <span class="li-required">required: false</span> <span class="li-normal">default: enable</span> </li>
    <li> <span class="li-head">persistence_inherit</span> - Enable (default) to use the persistence object specified in the virtual server configuration.<span class="li-normal">type: str</span> <span class="li-required">required: false</span> <span class="li-normal">default: enable</span> </li>
    <li> <span class="li-head">method</span> - If not using inheritance, select a load balancing method type.<span class="li-normal">type: str</span> <span class="li-required">required: false</span> </li>
    <li> <span class="li-head">persistence</span> - If not using inheritance, select a session persistence type.<span class="li-normal">type: str</span> <span class="li-required">required: false</span> </li>
    <li> <span class="li-head">comments</span> - Optional administrator note.<span class="li-normal">type: str</span> <span class="li-required">required: false</span> </li>
    <li> <span class="li-head">schedule_list</span> - Enable/disable schedule pool list.<span class="li-normal">type: str</span> <span class="li-required">required: false</span> <span class="li-normal">default: disable</span> </li>
    <li> <span class="li-head">schedule_pool_list</span> - Specify the schedule pool.<span class="li-normal">type: str</span> <span class="li-required">required: false</span> </li>
    <li> <span class="li-head">source_pool_list</span> - Specify source pool list.<span class="li-normal">type: str</span> <span class="li-required">required: false</span> </li>
    <li> <span class="li-head">names</span> - cotent routing list<span class="li-normal">type: list</span> <span class="li-required">required: false</span></li>
    <li> <span class="li-head">vdom</span> - VDOM name if enabled.<span class="li-normal">type: str</span> <span class="li-required">required: true(if VDOM is enabled)</span></li>
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
            - name: create
              fadcos_load_balance_content_routing:
               action: add
               name: test1
               type: l4-content-routing
               ip: 172.23.133.178/24
               method_inherit: disable
               method: LB_METHOD_LEAST_CONNECTION
               persistence_inherit: disable
               persistence: LB_PERSIS_SRC_ADDR
               schedule_list: disable
               pool: rs_pool
               comments: nothings

            - name: create
              fadcos_load_balance_content_routing:
               action: add
               name: test2
               type: l7-content-routing
               method_inherit: disable
               method: LB_METHOD_LEAST_CONNECTION
               persistence_inherit: disable
               persistence: LB_PERSIS_SRC_ADDR
               schedule_list: disable
               pool: rs_pool
               comments: nothings

            - name: edit
              fadcos_load_balance_content_routing:
               action: edit
               name: test1
               type: l7-content-routing
               method_inherit: enable
               persistence_inherit: enable
               schedule_list: disable
               pool: rs_pool
               comments: nothings

            - name: get
              fadcos_load_balance_content_routing:
               action: get

            - name: delete
              fadcos_load_balance_content_routing:
               action: remove
               names:
                    - test1

    
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
