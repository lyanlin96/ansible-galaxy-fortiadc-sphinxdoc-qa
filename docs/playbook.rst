
Run Your First Playbook
==============================

This document explains how to run your first FortiADC Ansible playbook.

--------------

With FortiADC Galaxy collection, you are always recommended to run
FortiADC module in ``httpapi`` manner. The first step is to prepare your
host inventory with which you can use ``ansible-vault`` to encrypt or
decrypt your secrets for the sake of confidentiality.

Prepare host inventory
~~~~~~~~~~~~~~~~~~~~~~

in our case we create a file named ``hosts``:

::

   [fortiadcs]
   fortiadc01 ansible_host=192.168.190.130 ansible_user="admin" ansible_password="password"
   fortiadc02 ansible_host=192.168.190.131 ansible_user="admin" ansible_password="password"

   [fortiadcs:vars]
   ansible_network_os=fortinet.fortiadc.fortiadc
   ansible_httpapi_use_ssl=yes
   ansible_httpapi_validate_certs=no
   ansible_httpapi_port=443


Write the playbook
~~~~~~~~~~~~~~~~~~

in the example: ``test.yml`` we are going to modify the fortiADC configurations.
device’s hostname:

::

   - hosts: fortiadc01
     collections:
     - fortinet.fortiadc
     connection: httpapi
     gather_facts: 'no'
     tasks:
     - name: Only https allow access to the device.
       fortiadc_system_interface:
         state: present
         system_interface:
           name: internal
           vdom: root
           allowaccess: 
             - https
             - http
             - ssh
             - ping

there are several options which might need you special care:

-  **connection** : ``httpapi`` is preferred.
-  **collections** : The namespace must be ``fortinet.fortiadc``
-  **ansible_httpapi_use_ssl** and **ansible_httpapi_port**: by
   default when your fortiADC device is licensed, the https is enabled.

Run the playbook
~~~~~~~~~~~~~~~~

::

   ansible-playbook -i hosts test.yml

you can also observe the verbose output by adding option at the tail:
``-vvv``.

