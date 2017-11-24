ansible-role-scl
=========

Install Sofware Collections for and CentOS.
Applying this role to other types of operating systems will simply "skip" the job.

Requirements
------------

Access to a repository containing packages, likely on the internet.

Role Variables
--------------

None known.

Dependencies
------------

- robertdebock/ansible-role-bootstrap

Example Playbook
----------------

```
---
- hosts: servers
  become: yes

  roles:
    - robertdebock.ansible-role-scl

  tasks:
    - name: install package from scl
      package:
        name: python27-python-pip
        state: present    
```

License
-------

Apache License, Version 2.0

Author Information
------------------

Robert de Bock <robert@meinit.nl>
