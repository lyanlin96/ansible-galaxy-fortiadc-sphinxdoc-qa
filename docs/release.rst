
Release Notes
==============================

Release Galaxy 1.2.1
--------------------

Release Targets
^^^^^^^^^^^^^^^

FortiADC Galaxy 1.2.1 is based on 1.2.0.

Features
^^^^^^^^^^^^^^^
- Restructure the "doc" directory to make it compatible with latest Read the Docs documentation format.

Release Galaxy 1.2.0
--------------------

Release Targets
^^^^^^^^^^^^^^^

FortiADC Galaxy 1.2.0 is based on 1.1.0.

Features
^^^^^^^^^^^^^^^
- Add modules idempotency.
- Rewrite modules so that users repeating module actions like 'add' and 'delete' with the same mkey will not encouter errors.
- FortiADC version: v7.2.x and v7.4.x

Notice
^^^^^^^^^^^^^^^
- When users attempt to add a duplicated entry, the ansible modules will not execute the action and generate message "Duplicate entry.". However, the ansible modules do not consider this action 'failed' and will continue executing the following tasks in a playbook.
- When users attempt to edit a non-existent entry, the ansible modules will not execute the action and generate message "Entry not found.". However, the ansible modules do not consider this action 'failed' and will continue executing the following tasks in a playbook.
- When users attempt to delete a non-existent entry, the ansible modules will not execute the action. However, the ansible modules do not consider this action 'failed' and will continue executing the following tasks in a playbook. 

Release Galaxy 1.1.0
--------------------

Release Targets
^^^^^^^^^^^^^^^

FortiADC Galaxy 1.1.0 is based on 1.0.2

Features
^^^^^^^^^^^^^^^
- Fix bugs of fadcos_virtual_server, fadcos_virtual_server and facdoc_headlth_check
- Add new modules: 
::

  - fadcos_error_page
  - fadcos_load_balance_content_routing
  - fadcos_load_balance_content_routing_child_match_condition
  - fadcos_load_balance_method
  - fadcos_load_balance_persistence
  - fadcos_load_balance_persistence_child_iso8583_bitmap
  - fadcos_load_balance_persistence_child_radius_attribute
  - fadcos_system_certificate_local
  - fadcos_system_cerificate_local_upload
  - fadcos_system_snmp_community
  - fadcos_system_snmp_community_child_host
  - fadcos_system_snmp_sysinfo
  - fadcos_system_snmp_user
  - fadcos_system_snmp_user_child_host
  - fadcos_system_time_ntp
  - fadcos_system_vdom

- FortiADC version: v7.1.4, v7.2.2 and v7.4.0

Notice
^^^^^^^^^^^^^^^

- For detailed configurations of fadcos_error_page and fadcos_system_cerificate_local_upload, please refer to the internal instructions within each module.

Release Galaxy 1.0.2
--------------------

Release Targets
^^^^^^^^^^^^^^^

FortiADC Galaxy 1.0.2 is based on 1.0.1.

Features
^^^^^^^^^^^^^^^
- Fix fortiadc_admin bug.
- Add modules fadcos_system_ha, fadcos_system_ha_remote_ip_monitor and fadcos_vm_license
- FortiADC version: v7.0.0, v7.0.1, v7.0.2, v7.0.3, v7.1.0 and v7.2.0

Release Galaxy 1.0.1
--------------------

Release Targets
^^^^^^^^^^^^^^^

FortiADC Galaxy 1.0.1 is based on 1.0.0.

Features
^^^^^^^^^^^^^^^
- Fix Galaxy link.
- Add document.

Release Galaxy 1.0.0
--------------------

Release Targets
^^^^^^^^^^^^^^^

It is the initial release of fortiADC Ansible Project.

Features
^^^^^^^^^^^^^^^
- FortiADC JRPC URLs coverage (20 modules).
- FortiADC version: v7.0.0, v7.0.1, v7.0.2, v7.0.3 and v7.1.0

