:source: fadcos_system_certificate_local_upload.py

:orphan:

.. fadcos_system_certificate_local_upload:

fadcos_system_certificate_local_upload -- upload local certificate to Fortinet's FortiADC
++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++

.. versionadded:: 1.1.0

.. contents::
   :local:
   :depth: 1


Synopsis
--------
- Import Local Certificate in Manage Certificates Page  



Requirements
------------
The below requirements are needed on the host that executes this module.

- ansible>=2.8

This module behaves differently across various system environments:

- In Python versions < 3.7, the supported type for uploaded certificate file are CertKey, Automated

- In Python versions >= 3.7, the supported type for uploaded certificate file are CertKey, Automated, PKCS12 
- Additionally, this support is restricted to FortiADC systems with versions 7.4.0 and later.

- In Python versions >= 3.10, the supported type for uploaded certificate file are CertKey, Automated 
- Additionally, this support is restricted to FortiADC systems with versions 7.4.0 and later.

We recommend users to utilize Python versions 3.7 with FotiADC 7.4.0 and later 

FortiADC Version Compatibility
------------------------------


.. raw:: html

 <br>
 <table>
 <tr>
 <td></td>
 <td><code class="docutils literal notranslate">v7.4.0 </code></td>
 </tr>
 <tr>
 <td>fadcos_system_certificate_local_upload</td>
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
    <li> <span class="li-head">type</span> - Specify the type of Certificate.<span class="li-normal">type: str</span> <span class="li-required">required: trur (if action is add) </span> </li>
    <li> <span class="li-head">certificate_file</span> - Specify the source of certificate file.<span class="li-normal">type: int</span> <span class="li-required">required: false</span> <span class="li-normal">default: 300</span> </li>
    <li> <span class="li-head">key_file</span> - Specify the source of key file if necessary.<span class="li-normal">type: str</span> <span class="li-required">required: false</span> <span class="li-normal">default: 32</span> </li>
    <li> <span class="li-head">passwd</span> - Specify the password if necessary.<span class="li-normal">type: str</span> <span class="li-required">required: false</span> <span class="li-normal">default: </span> </li>
    <li> <span class="li-head">upload</span> - Specify the input type. (upload/text)<span class="li-normal">type: str</span> <span class="li-required">required: false</span> <span class="li-normal">default: upload</span> </li>
    <li> <span class="li-head">cert</span> - Specify the content of certificate file if upload is text.<span class="li-normal">type: str</span> <span class="li-required">required: false</span> </li>
    <li> <span class="li-head">key</span> - SSpecify the content of key file if upload is text.<span class="li-normal">type: str</span> <span class="li-required">required: false</span> </li>
    <li> <span class="li-head">acme_service</span> - Specifies the ACME Service if certificate type is automated.<span class="li-normal">type: str</span> <span class="li-required">required: false</span> </li>
    <li> <span class="li-head">ca_group</span> - Specify the name of the CA Group if certificate type is automated.<span class="li-normal">type: str</span> <span class="li-required">required: false</span> </li>
    <li> <span class="li-head">challenge_type</span> - Specifies the challenge types if certificate type is automated. (tls-alpn-01/dns-01)<span class="li-normal">type: str</span> <span class="li-required">required: false</span> </li>
    <li> <span class="li-head">challenge_wait</span> - Specify the ACME DNS-01 challenge wait time in minutes if challenge_type is dns-01. (Range: 1-1440 minutes).<span class="li-normal">type: str</span> <span class="li-required">required: false</span> </li>
    <li> <span class="li-head">renew_win</span> - Specify a renew window (in minutes) to automatically renew the certificate before it expires if challenge_type is tls-alpn-01. (Range: 0-43200 minutes).<span class="li-normal">type: str</span> <span class="li-required">required: false</span> </li>
    <li> <span class="li-head">domain</span> - Specify the web server domain to be protected if certificate type is automated.<span class="li-normal">type: str</span> <span class="li-required">required: false</span> </li>
    <li> <span class="li-head">email</span> - Enter the email address that will receive notifications regarding the status if certificate type is automated.<span class="li-normal">type: str</span> <span class="li-required">required: false</span> </li>
    <li> <span class="li-head">key_type</span> - Select either of the following key types. (RSA/ECDSA) If the challenge_type is tls-alpn-01, the key_type must match the key type of the "placeholder"<span class="li-normal">type: str</span> <span class="li-required">required: false</span> <span class="li-normal"> default: RSA </span> </li>
    <li> <span class="li-head">key_size</span> - Specify the key_size if key_type is RSA. (2048/3072/4096)<span class="li-normal">type: str</span> <span class="li-required">required: false</span> <span class="li-normal"> d\efault: 2048</span> </li>
    <li> <span class="li-head">curve_name</span> - Specify the curve_name if key_type is ECDSA. (P256/P384/P521)<span class="li-normal">type: str</span> <span class="li-required">required: false</span> </li>
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
            - name: add CertKey
              fadcos_system_certificate_local_upload:
               action: add
               type: CertKey
               name: test_certkey_text
               cert: "-----BEGIN CERTIFICATE-----\r\nMIIEdDCCA1ygAwIBAgICEAAwDQYJKoZIhvcNAQELBQAwUjELMAkGA1UEBhMCVFcx\r\nFTATBgNVBAgMDE1pY2stUm9vdC1DQTEZMBcGA1UECgwQTWljay1Sb290LUNBIEx0\r\nZDERMA8GA1UEAwwIbWljay5jb20wHhcNMTkwNDE2MDUwOTE0WhcNMjcwNzAzMDUw\r\nOTE0WjBUMQswCQYDVQQGEwJUVzEVMBMGA1UECAwMTWljay1Sb290LUNBMRkwFwYD\r\nVQQKDBBNaWNrLVJvb3QtQ0EgTHRkMRMwEQYDVQQDDAptaWNrMDEuY29tMIIBIjAN\r\nBgkqhkiG9w0BAQEFAAOCAQ8AMIIBCgKCAQEAtcduRHIsD+HSiysbV1w3NeSfO5zr\r\nhGzdZy2qg3uUpXUtCdeJOk+PL+nUK3drGd+sVC2sB1cOPxQNB0SODOxDQdBDwxtl\r\nisUYqo2IzHhCY/SXDNsshhp6mQH1yrZRmguuBvU0zEtgUd8HG/TH54XPC8RrUEGt\r\ntmW70lGI7D5eUKjjf6h/5CwDRL9BzNPxeM7LisSwtkDteFLVGZwW9BMMp8uw6wET\r\n3CuhVIQe7iCEQ2tzxXJo729YdxAxvzxcl5QxaS2lUdagyYI0QFmDPR+pfxHg60Dh\r\ngKCgPzeVfVA7NXwjQnyYxtFeVCMzxzLa6EzkuPd9j1hmS0vnz/VTND/DKwIDAQAB\r\no4IBUDCCAUwwCQYDVR0TBAIwADARBglghkgBhvhCAQEEBAMCBkAwMwYJYIZIAYb4\r\nQgENBCYWJE9wZW5TU0wgR2VuZXJhdGVkIFNlcnZlciBDZXJ0aWZpY2F0ZTAdBgNV\r\nHQ4EFgQUSn1X57XIYKSGpOtdnRypvrR3M1YwgY8GA1UdIwSBhzCBhIAU+5C1YZQW\r\nuappXq9Emw0Fci0kEz2hVqRUMFIxCzAJBgNVBAYTAlRXMRUwEwYDVQQIDAxNaWNr\r\nLVJvb3QtQ0ExGTAXBgNVBAoMEE1pY2stUm9vdC1DQSBMdGQxETAPBgNVBAMMCG1p\r\nY2suY29tghR9fTArcRwtamYDWFLqnmoeMVTesDAOBgNVHQ8BAf8EBAMCBaAwEwYD\r\nVR0lBAwwCgYIKwYBBQUHAwEwIQYDVR0RBBowGIIKbWljazAyLmNvbYIKbWljazAz\r\nLmNvbTANBgkqhkiG9w0BAQsFAAOCAQEAM2XBgNK9p01G1Byb2QaiEuu+sGne5AOn\r\nf8AVkJ4Jvszi6WsQX83TBkGUGjc2tZk9ByDfOPwfyUNbqGLLdMr7C5s0czhaLqNx\r\nZJ/Qj+bvwIH581VX3rlURQ4t1tjCb5RKZnqfMOJNaxwNMVTPGA8QvxoyD9UGbmib\r\nA2tbk2SxWHMseVGc3Y3D0r3GMFMsAlTFJpAWKInlGnVU57wWUSumlWexdxliE0sD\r\nuLm+tRd8ZTtkXwtwCowUiIoMAT47CkzVLg6zUAmVz+4SBAg9+KxCpMT682SJWyOz\r\n8CR6X8KNTF3GE3kJEhjdChDczFrTXmMUksrdVySr/awpqDhShhTpLw==\r\n-----END CERTIFICATE-----\r\n"
               key: "-----BEGIN RSA PRIVATE KEY-----\r\nMIIEowIBAAKCAQEAtcduRHIsD+HSiysbV1w3NeSfO5zrhGzdZy2qg3uUpXUtCdeJ\r\nOk+PL+nUK3drGd+sVC2sB1cOPxQNB0SODOxDQdBDwxtlisUYqo2IzHhCY/SXDNss\r\nhhp6mQH1yrZRmguuBvU0zEtgUd8HG/TH54XPC8RrUEGttmW70lGI7D5eUKjjf6h/\r\n5CwDRL9BzNPxeM7LisSwtkDteFLVGZwW9BMMp8uw6wET3CuhVIQe7iCEQ2tzxXJo\r\n729YdxAxvzxcl5QxaS2lUdagyYI0QFmDPR+pfxHg60DhgKCgPzeVfVA7NXwjQnyY\r\nxtFeVCMzxzLa6EzkuPd9j1hmS0vnz/VTND/DKwIDAQABAoIBAHPlSvBoup8Fo28H\r\ndM8mBC1gLgWb7qznm+GExApAaG11X9m+icebofcyZguwf6Bncz/YPq4PWw3sgsH3\r\ne3nRyK/VUN68QOlQ8IEM7AMxSWLhNs0DkEeP6kpTbZpo024btEDLZXY7OJX6VFYG\r\nos2CCpe+C42H0nFQO4fEZD/7I7bYYjjge0/HTbD8SjMkWn2Cfjz4ML2sBSdh0Df2\r\nYC9Hr21WxoNlZDsogCiKIISUWBbNPo029qlxcBhkW+OFzaNSSrO4tX0m4wJqOf13\r\ngWQXLCajuQeGH9OruU+8x3StBHTSoVW9mPBhZkP6dhHIm3ycp/wE/kDGbbI0cRn3\r\nIStZTMECgYEA8LXu32oHL0LVvY1Z9r8bzYELRz1f5Plnqmi9hr03vE3uWfoZL6vd\r\ngksGz/Wo5kTGMTj1cF/PTs/Kjtoke7CQ79TteAwY3ZMwUGIC9rObKXmKssSTlXiA\r\nmHSF7NOHrkbP0gGmlxohtj+ImaMKFpI4dQFlalg1D6ouAERc9M2Cm6cCgYEAwVM9\r\n49IboQf6TxI+1YMqRPbpm1UeYaGgeM7sbvK6YmgKaKu5ImJRxudQD+XDXTpcZHOO\r\nJq5CHhS98HwYUAKbpxlmmKzXAPY5/kn2r0QcPvHGtFTacV6QY5Lg9ldpmn93S6nU\r\nl92jBO3UU/nq1HqYKGXI6GQOH+0Gv+caValh/N0CgYA+SPVcfhUJ16Ny/uZugJjz\r\nHhcLAgiUOSzn3V5dRQzs/sVUJvDpcvFIS52hphFkNBuMlQ59W21LGV1yhWO3VcLL\r\nLC+eRpMQkouH4TSfHW5i1v5ar574qEuuJ0iYNUwAfnY8Aw1WP/7FJ79y8cskeAV/\r\n0TKqx9RDD2gDzay3841+NQKBgA8zXV1patS5jNvkwl4FZzBu/aVCBxaEH9r/4iVD\r\nHpaYOaFLR05FzspF68ykMz1EVnlrgJTYBMjatqiPCVZZLiXwYFnG1Uz1D1BIPoY/\r\nY70rQ4VwWpCpb870gI2+B8anGRkw7E9YlPXRQW2s6+LzFL2wayCipV2rRGmYYUC1\r\nBchdAoGBAM78RwvGRGDDh4NtyCNIFbcHkXRNhd+F7dij7KOfwPzT4kB8F3Z4EG86\r\ntdcAt/2P5XpTutCczgdjNtTwWGX9PqFkbmh6A8H99prPmXRIJUTI22zrNX0K0jeU\r\nu/QDVZd9vB+dt+41ecgbjVyK2dUnbUxmIcPWCyLjLgnaiHzj2FcW\r\n-----END RSA PRIVATE KEY-----\r\n"
               upload: text
               passwd: test

            - name: add PKCS12
              fadcos_system_certificate_local_upload:
               action: add
               type: PKCS12
               name: test
               certificate_file: rootCA-Client-RSA.p12

            - name: add CertKey
              fadcos_system_certificate_local_upload:
               action: add
               type: CertKey
               name: test_certkey
               certificate_file: rootCA-Serve-RSA.crt
               key_file: rootCA-Serve-RSA.key
               passwd: test
            
            - name: add Automated
              fadcos_system_certificate_local_upload:
               action: add
               type: Automated
               name: test_automated
               passwd: test
               acme_service: "encrypt"
               ca_group: ""
               challenge_type: "dns-01"
               challenge_wait: "3"
               domain: "test.com"
               email: "test@fortinet.com"
               key_size: "2048"
               key_type: "RSA"

    
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
