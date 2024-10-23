:source: fadcos_waf_adaptive_learning_child_url_list.py

:orphan:

.. fadcos_waf_adaptive_learning_child_url_list:

fadcos_waf_adaptive_learning_child_url_list -- Configure the URL List settings of an Adaptive Learning policy
++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++

.. versionadded:: 1.3.0

.. contents::
   :local:
   :depth: 1


Synopsis
--------
- Configure the URL List settings of an Adaptive Learning polic



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
 <td>fadcos_waf_adaptive_learning_child_url_list</td>
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
    <li> <span class="li-head">host</span> - Specify the HTTP Host header. If Host Status is enabled, the policy matches only if the Host header matches this value. Complete, exact matching is required.<span class="li-normal">type: str</span> <span class="li-required">required: false</span> </li>
    <li> <span class="li-head">host_status</span> - The Host option is available if Host Status is enabled.<span class="li-normal">type: str</span> <span class="li-required">required: false</span> </li>
    <li> <span class="li-head">url</span> - The literal URL, such as /index.php, or a regular expression, such as ^/*.php that the HTTP request must contain in order to match the rule. Multiple URLs are supported.<span class="li-normal">type: str</span> <span class="li-required">required: false</span></li>
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
            - name: Add WAF Adaptive Learning Child URL list entry
              fadcos_waf_adaptive_learning_child_url_list:
                action: add
                url: /home/test1
                name: al2

            - name: Add duplicate WAF Adaptive Learning Child URL list entry
              fadcos_waf_adaptive_learning_child_url_list:
                action: add
                url: /home/test1
                name: al2
                id: 1

            - name: Get WAF Adaptive Learning Child URL list entry
              fadcos_waf_adaptive_learning_child_url_list:
                action: get
                name: al2
                id: 2

            - name: edit WAF another Adaptive Learning Entry
              fadcos_waf_adaptive_learning_child_url_list:
                action: edit
                name: al2
                id: 2
                host_status: enable
                host: 3.3.3.4
                url: /home/test2

            - name: Get all WAF Adaptive Learning Child URL list
              fadcos_waf_adaptive_learning_child_url_list:
                action: get
                name: al2

            - name: delete WAF another Adaptive Learning Entry
              fadcos_waf_adaptive_learning_child_url_list:
                action: delete
                name: al2
                id: 5

            - name: edit non-existant WAF Adaptive Learning Entry
              fadcos_waf_adaptive_learning_child_url_list:
                action: edit
                name: al2
                id: 88
                host: 66.66.66.0
            
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
