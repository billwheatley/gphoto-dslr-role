gphoto-dslr-role
=========

Ansible role to install gPhoto so that you can use a DSLR as a webcam.

This role was derived from [Ben Chapman's blog post](https://medium.com/nerdery/dslr-webcam-setup-for-linux-9b6d1b79ae22)

This was also designed as part of a desktop provisioning playbooks found here <https://github.com/billwheatley/provision-desktop>

Requirements
------------

- A distribution with `dnf` or `apt`

Role Variables
--------------

none

Example Playbook
----------------

```yaml
- name: My Playbook
  hosts: all
  roles:
    - role: gphoto-dslr-role
```

License
-------

GPLv2

Author Information
------------------

Contact via [Github](https://github.com/billwheatley/)
