ansible-role-rhv-vm
===================

Create virtual machine into RHV, and do basic initialisations for it. This is
tested with RHEL7.

Requirements
------------

It is required to install oVirt SDK onto tower machine in order to use this
role. RPM name is python-ovirt-engine-sdk4.

Role Variables
--------------

There is list of variables in defaults/main.yml which can be overridden in
vault or in Tower. You need to modify them to use this role.

Dependencies
------------

We also have infra_playbooks collection, which this module is part of.
See [our blogs on github](https://redhatnordicssa.github.io/) for more info.

Example Playbook
----------------

```
- include_role:
    name: ansible-role-rhv-vm
  vars:
    rhv_vm_name: "{{ short_hostname }}"
    rhv_vm_domain: "{{ domain }}"
    rhv_vm_ip: "{{ phpipam_ip }}"
    rhv_vm_netmask: "{{ phpipam_netmask }}"
    rhv_vm_gw: "{{ phpipam_gw }}"
    rhv_vm_dns1: "{{ phpipam_nameserver1 }}"
    rhv_vm_state: running
```


License
-------

BSD

Author Information
------------------

Peter Gustafsson, pgustafs@redhat.com
[Red Hat SAs](https://redhatnordicssa.github.io/)
