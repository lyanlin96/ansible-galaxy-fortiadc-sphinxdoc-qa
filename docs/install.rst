
Install FortiADC Ansible Galaxy
==================================

This document explains how to install the FortiADC Ansible Galaxy
Collection.

--------------

Install Python
~~~~~~~~~~~~~~~

-  Follow steps in https://www.python.org/ to install Python2(>= 2.7.12) or Python3 on your
   host.

Install Ansible Core
~~~~~~~~~~~~~~~~~~~~

-  Follow instructions in
   https://docs.ansible.com/ansible/latest/installation_guide/intro_installation.html
   to install Ansible
-  The Ansible core version requirement: >= 2.8

Install FortiADC Galaxy Collection
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

The FortiADC Ansible Galaxy will support multilple FortiADC major releases,
you can install the latest collection by default via command
``ansible-galaxy collection install fortinet.fortiadc``. you can also
choose another galaxy version to match your FortiADC device.

Please see the `versionig notes`_ for more recently released collections
and install the ones which are marked ``latest`` for your devices.

.. _versionig notes: version.html

