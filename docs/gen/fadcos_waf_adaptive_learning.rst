:source: fadcos_waf_adaptive_learning.py

:orphan:

.. fadcos_waf_adaptive_learning:

fadcos_waf_adaptive_learning -- Configuring an Adaptive Learning policy
++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++

.. versionadded:: 1.3.0

.. contents::
   :local:
   :depth: 1


Synopsis
--------
- Configuring an Adaptive Learning policy



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
 <td>fadcos_waf_adaptive_learning</td>
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
    <li> <span class="li-head">name</span> - Specify the name of the adaptive learning policy.<span class="li-normal">type: str</span> <span class="li-required">required: true</span> </li>
    <li> <span class="li-head">fp_threshold</span> - 	Specify the threshold at which triggered events should be considered a false positive.<span class="li-normal">type: str</span> <span class="li-required">required: false</span> </li>
    <li> <span class="li-head">learning_time</span> - The learning time of adaptive learning policy.<span class="li-normal">type: str</span> <span class="li-required">required: false</span> </li>
    <li> <span class="li-head">sampling_rate</span> - Specify the percentage of received requests and their responses that will be sampled.<span class="li-normal">type: str</span> <span class="li-required">required: false</span></li>
    <li> <span class="li-head">security_action</span> - Set the action to take after you accept the recommendation for the WAF policy from Adaptive Learning.<span class="li-normal">type: str</span> <span class="li-required">required: false</span></li>
    <li> <span class="li-head">vdom</span> - VDOM name if enabled.<span class="li-normal">type: str</span> <span class="li-required">required: true(if VDOM is enabled)</li>
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
            - name: Add WAF Adaptive Learning Entry
              fadcos_waf_adaptive_learning:
                action: add
                learning_time: 9900
                name: al1

            - name: Get WAF Adaptive Learning Entry
              fadcos_waf_adaptive_learning:
                action: get
                name: al1

            - name: Add WAF another Adaptive Learning Entry
              fadcos_waf_adaptive_learning:
                action: add
                name: al2
                security_action: captcha
                fp_threshold: 500
                learning_time: 12000
                sampling_rate: 70
                status: enable

            - name: Get WAF Adaptive Learning Entry 1
              fadcos_waf_adaptive_learning:
                action: get
                name: al2
        
            - name: Edit WAF Adaptive Learning Entry
              fadcos_waf_adaptive_learning:
                action: edit
                name: al2
                sampling_rate: 75
                fp_threshold: 2456
                learning_time: 11111
                security_action: block
                status: enable

            - name: Get WAF Adaptive Learning Entry 2
              fadcos_waf_adaptive_learning:
                action: get
                name: al2

            - name: Get non-existant WAF Adaptive Learning Entry
              fadcos_waf_adaptive_learning:
                action: get
                name: al_none

            - name: Delete 1st WAF Adaptive Learning Entry
              fadcos_waf_adaptive_learning:
                action: delete
                name: al1

            - name: Delete 2nd WAF Adaptive Learning Entry
              fadcos_waf_adaptive_learning:
                action: delete
                name: al2
            
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

- Joseph Chen


.. hint::
    If you notice any issues in this documentation, you can create a pull request to improve it.
