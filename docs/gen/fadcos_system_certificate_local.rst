:source: fadcos_system_certificate_local.py

:orphan:

.. fadcos_system_certificate_local:

fadcos_system_certificate_local -- Generate Certificate Signing Request in Fortinet's FortiADC
++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++

.. versionadded:: 1.1.0

.. contents::
   :local:
   :depth: 1


Synopsis
--------
- Generate certificate signing request of Local Certificate in Manage Certificates Page 



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
 <td>fadcos_system_certificate_local</td>
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
    <li> <span class="li-head">name</span> - config certificate name <span class="li-normal">type: str</span> <span class="li-required">required: false</span> </li>
    <li> <span class="li-head">id_type</span> - Specify the ID type.<span class="li-normal">type: str</span> <span class="li-required">required: false</span> </li>
    <li> <span class="li-head">ip</span> - Specify the IP if the id type is ip.<span class="li-normal">type: int</span> <span class="li-required">required: false</span> <span class="li-normal">default: 192.0.2.1</span> </li>
    <li> <span class="li-head">domain</span> - Specify the Domain Name if the id type is domain.<span class="li-normal">type: str</span> <span class="li-required">required: false</span> <span class="li-normal">default: www.example.com</span> </li>
    <li> <span class="li-head">email</span> - Specify the Email if the id type is email.<span class="li-normal">type: str</span> <span class="li-required">required: false</span> <span class="li-normal">default: admin@example.com</span> </li>
    <li> <span class="li-head">orgUnit</span> - Specify the Organization Unit.<span class="li-normal">type: list</span> <span class="li-required">required: false</span> </li>
    <li> <span class="li-head">org</span> - Specify the Organization.<span class="li-normal">type: str</span> <span class="li-required">required: false</span> </li>
    <li> <span class="li-head">city</span> - Specify the City/Locality.<span class="li-normal">type: str</span> <span class="li-required">required: false</span> </li>
    <li> <span class="li-head">state</span> - Specify the State/Province.<span class="li-normal">type: str</span> <span class="li-required">required: false</span> </li>
    <li> <span class="li-head">country</span> - Specify the Country/Region.<span class="li-normal">type: str</span> <span class="li-required">required: false</span> <span class="li-normal">default: AF</span> </li>
    <li> <span class="li-head">orgEmail</span> - Specify the Email Address.<span class="li-normal">type: str</span> <span class="li-required">required: false</span> </li>
    <li> <span class="li-head">san</span> - Specify the Subject Alternative Name.<span class="li-normal">type: str</span> <span class="li-required">required: false</span> </li>
    <li> <span class="li-head">enc_meth</span> - Specify the Private Key Encryption.<span class="li-normal">type: str</span> <span class="li-required">required: false</span> <span class="li-normal">default: aes128</span> </li>
    <li> <span class="li-head">k_pwd</span> - Specify the Private Key Password.<span class="li-normal">type: str</span> <span class="li-required">required: false</span> </li>
    <li> <span class="li-head">keyType</span> - Specify the Key Type in Key Information. (1:RSA, 2:ECDSA)<span class="li-normal">type: str</span> <span class="li-required">required: false</span> <span class="li-normal">default: 1</span> </li>
    <li> <span class="li-head">keySize</span> - Specify the Key Size if keyType is 1(RSA).<span class="li-normal">type: str</span> <span class="li-required">required: false</span> <span class="li-normal">default: 512</span> </li>
    <li> <span class="li-head">hash</span> - Specify the Hash Function if keyType is 1(RSA).<span class="li-normal">type: str</span> <span class="li-required">required: false</span> <span class="li-normal">default: SHA1</span> </li>
    <li> <span class="li-head">keySizeECDSA</span> - Specify the Key Size if keyType is 2(ECDSA).<span class="li-normal">type: str</span> <span class="li-required">required: false</span> <span class="li-normal">default: 256</span> </li>
    <li> <span class="li-head">enrollMethod</span> - Specify the Enrollment Method in Enrollment Information. (file/scep) <span class="li-normal">type: str</span> <span class="li-required">required: false</span> <span class="li-normal">default: file</span> </li>
    <li> <span class="li-head">scep_url</span> - Specify URL if Enrollment Method is scep<span class="li-normal">type: str</span> <span class="li-required">required: true (if Enrollment Method is scep)</span> </li>
    <li> <span class="li-head">c_pwd</span> - Specify the Challenge Password if Enrollment Method is scep<span class="li-normal">type: str</span> <span class="li-required">required: true (if Enrollment Method is scep)</span> </li>
    <li> <span class="li-head">ca_id</span> - Specify the CA Identifer if Enrollment Method is scep<span class="li-normal">type: str</span> <span class="li-required">required: true (if Enrollment Method is scep)</span> </li>
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
              fadcos_system_certificate_local:
               action: add
               name: test
               id_type: ip
               ip: '192.0.2.1'
               orgUnit:
                      - test1
                      - test2
               org: 'MyCorp Inc.'
               city: Sunnyvale
               state: CA
               country: AF
               orgEmail: 'admin@exammple.com'
               san: 'IP:192.168.1.102'
               enc_meth: aes128
               k_pwd: test
               keyType: '1'
               keySize: '2048'
               hash: SHA256
               enrollMethod: file

            - name: create
              fadcos_system_certificate_local:
               action: add
               name: test2
               id_type: domain
               domain: www.example.com
               orgUnit:
                      - test3
               org: MyCorp2 Inc.
               city: Sunnyvale
               country: AF
               state: CA
               orgEmail: admin@exammple.com
               san: 'DNS:www.a.b'
               enc_meth: aes192
               k_pwd: test
               keyType: '2'
               keySizeECDSA: '512'
               enrollMethod: file

            - name: get
              fadcos_system_certificate_local:
               action: get

            - name: delete
              fadcos_system_certificate_local:
               action: remove
               name: test

            - name: delete
              fadcos_system_certificate_local:
               action: remove
               name: test2

    
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
