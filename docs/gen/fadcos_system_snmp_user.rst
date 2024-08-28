:source: fadcos_system_snmp_user.py

:orphan:

.. fadcos_system_snmp_user:

fadcos_system_snmp_user -- configure SNMP community settings in Fortinet's FortiADC
+++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++

.. versionadded:: 1.1.0

.. contents::
   :local:
   :depth: 1


Synopsis
--------
- Configure SNMP community settings of SNMPv3 in SNMP Page 



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
 <td>fadcos_system_snmp_user</td>
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
    <li> <span class="li-head">name</span> - Specify the name of the SNMP community.<span class="li-normal">type: str</span> <span class="li-required">required: false</span> </li>
    <li> <span class="li-head">security_level</span> - Specify the security level. (authnopriv/authpriv/noauthnopriv)<span class="li-normal">type: str</span> <span class="li-required">required: false</span> </li>
    <li> <span class="li-head">query_port</span> - Port number on which the system listens for SNMP queries from the SNMP managers in this community.<span class="li-normal">type: str</span> <span class="li-required">required: false</span> <span class="li-normal">default: 161</span> </li>
    <li> <span class="li-head">query_status</span> - Enable/disable SNMP queries.<span class="li-normal">type: int</span> <span class="li-required">required: false</span> <span class="li-normal">default: enable</span> </li>
    <li> <span class="li-head">auth_proto</span> - Specify the auth algorithm. (sha1/md5)<span class="li-normal">type: str</span> <span class="li-required">required: true (if security_level is authpriv or authnopriv.) </span> </li>
    <li> <span class="li-head">auth_pwd</span> - Specify the auth password.<span class="li-normal">type: str</span> <span class="li-required">required: true (if security_level is authpriv or authnopriv.) </span> </li>
    <li> <span class="li-head">privacy_proto</span> - Specify the private algorithm. (aes/des)<span class="li-normal">type: str</span> <span class="li-required">required: true (if security_level is authpriv.) </span> </li>
    <li> <span class="li-head">privacy_pwd</span> - Specify the private password.<span class="li-normal">type: str</span> <span class="li-required">required: true (if security_level is authpriv.) </span> </li>
    <li> <span class="li-head">names</span> - SNMP community name list<span class="li-normal">type: list</span> <span class="li-required">required: false</span></li>
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
              fadcos_system_snmp_user:
               action: add
               auth_proto: sha1
               auth_pwd: '123'
               name: test
               privacy_proto: aes
               privacy_pwd: '123'
               query_port: '161'
               security_level: authpriv
               status: enable

            - name: edit
              fadcos_system_snmp_user:
               action: edit
               auth_proto: sha1
               auth_pwd: '123'
               name: test
               privacy_proto: aes
               privacy_pwd: '123'
               query_port: '161'
               security_level: authpriv
               status: disable

            - name: get
              fadcos_system_snmp_user:
               action: get

            - name: remove
              fadcos_system_snmp_user:
               action: remove
               names:
                    - test
            
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
