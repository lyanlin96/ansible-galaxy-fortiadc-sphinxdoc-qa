:source: fadcos_system_ha.py

:orphan:

.. fadcos_system_ha:

fadcos_system_ha -- HA configuration in Fortinet's FortiADC
++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++

.. versionadded:: 1.0.2

.. contents::
   :local:
   :depth: 1


Synopsis
--------
- Configure FortiADC HA



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
 <td><code class="docutils literal notranslate">v7.2.0 </code></td>
 <td><code class="docutils literal notranslate">v7.2.2 </code></td>
 <td><code class="docutils literal notranslate">v7.4.0 </code></td>
 </tr>
 <tr>
 <td>fadcos_system_ha</td>
 <td>yes</td>
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
    <li> <span class="li-head">mgmt_interface</span> - Management interface. <span class="li-normal">type: str</span> <span class="li-required">required: false</span> </li>
    <li> <span class="li-head">local_node_id</span> - local node id (0-7). <span class="li-normal">type: str</span> <span class="li-required">required: false</span> </li>
    <li> <span class="li-head">peer_address</span> - Fort unicast peer ip address. <span class="li-normal">type: str</span> <span class="li-required">required: false</span> </li>
    <li> <span class="li-head">group_name</span> - group name. <span class="li-normal">type: str</span> <span class="li-required">required: false</span> </li>
    <li> <span class="li-head">sync_l4_persistent</span> - sync l4 persistent. <span class="li-normal">type: str</span> <span class="li-required">required: false</span> </li>
    <li> <span class="li-head">monitor_enable</span> - interface list to track. <span class="li-normal">type: str</span> <span class="li-required">required: false</span> </li>
    <li> <span class="li-head">hbdev</span> - heartbeat port. <span class="li-normal">type: str</span> <span class="li-required">required: false</span> </li>
    <li> <span class="li-head">mgmt_ip_allowaccess</span> - Allow access with the management ip address. <span class="li-normal">type: str</span> <span class="li-required">required: false</span> </li>
    <li> <span class="li-head">config_priority</span> - ha config priority. <span class="li-normal">type: str</span> <span class="li-required">required: false</span> 
    <li> <span class="li-head">hb_lost_threshold</span> - lost heartbeat threshold (1-60). <span class="li-normal">type: str</span> <span class="li-required">required: false</span> 
    <li> <span class="li-head">override</span> - override on resurge. <span class="li-normal">type: str</span> <span class="li-required">required: false</span>
    <li> <span class="li-head">groupid</span> - group id (0-31). <span class="li-normal">type: str</span> <span class="li-required">required: false</span>
    <li> <span class="li-head">node_list</span> - node id. <span class="li-normal">type: str</span> <span class="li-required">required: false</span>
    <li> <span class="li-head">local_address</span> - For unicast local listening ip address. <span class="li-normal">type: str</span> <span class="li-required">required: false</span>
    <li> <span class="li-head">mgmt_ip</span> - IP address of management interface. <span class="li-normal">type: str</span> <span class="li-required">required: false</span>
    <li> <span class="li-head">sync_l4_connection</span> - sync l4 connection. <span class="li-normal">type: str</span> <span class="li-required">required: false</span>
    <li> <span class="li-head">datadev</span> - data port. <span class="li-normal">type: str</span> <span class="li-required">required: false</span>
    <li> <span class="li-head">arp_num</span> - num for sending (1-60). <span class="li-normal">type: str</span> <span class="li-required">required: false</span>
    <li> <span class="li-head">failover_hold_time</span> - failover hold time for remote ip (60-86400 sec). <span class="li-normal">type: str</span> <span class="li-required">required: false</span>
    <li> <span class="li-head">interval</span> - heartbeat interval. <span class="li-normal">type: str</span> <span class="li-required">required: false</span>
    <li> <span class="li-head">arp_interval</span> - interval for sending arp (1-20 sec). <span class="li-normal">type: str</span> <span class="li-required">required: false</span>
    <li> <span class="li-head">mode</span> - high availability mode. <span class="li-normal">type: str</span> <span class="li-required">required: false</span>
    <li> <span class="li-head">mgmt_status</span> - Management status enable/disable. <span class="li-normal">type: str</span> <span class="li-required">required: false</span>
    <li> <span class="li-head">interface_list</span> - interface list to track. <span class="li-normal">type: str</span> <span class="li-required">required: false</span>
    <li> <span class="li-head">sync_l7_persistent</span> - sync http persistent. <span class="li-normal">type: str</span> <span class="li-required">required: false</span>
    <li> <span class="li-head">hbtype</span> - heartbeat type. <span class="li-normal">type: str</span> <span class="li-required">required: false</span>
    <li> <span class="li-head">failover_threshold</span> - failover threshold for remote ip (1-64). <span class="li-normal">type: str</span> <span class="li-required">required: false</span>
    <li> <span class="li-head">priority</span> - ha priority (0-9). <span class="li-normal">type: str</span> <span class="li-required">required: false</span>
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
              vars:
               ansible_command_timeout: 60
               #ha setting need more time so set timeout to 60s
              fadcos_system_ha:
               mgmt_interface:
               local_node_id: 0
               peer_address: 0.0.0.0
               group_name: 1
               sync_l4_persistent: disable
               monitor_enable: disable
               hbdev: port5
               mgmt_ip_allowaccess:
               config_priority: 100
               hb_lost_threshold: 6
               isSystemAdmin: True
               override: disable
               groupid: 0
               node_list: 0
               local_address: 0.0.0.0
               isSystemWritable: True
               mgmt_ip: 0.0.0.0/0
               sync_l4_connection: disable
               datadev: port2
               arp_num: 5
               failover_hold_time: 120
               interval: 2
               arp_interval: 6
               mode: active-passive
               mgmt_status: disable
               interface_list: port2
               sync_l7_persistent: disable
               hbtype: multicast
               failover_threshold: 5
               priority: 1

    


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
