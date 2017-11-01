Role Name
=========

Have Docker available.

Requirements
------------

Pythons pip should be available. robertdebock.python-pip resolves this dependency.

Role Variables
--------------

None known.

Dependencies
------------

robertdebock.python-pip

Example Playbook
----------------

```
---
- hosts: servers
  become: yes
  roles:
    - docker
```

License
-------

Apache License, Version 2.0

Author Information
------------------

Robert de Bock <robert@meinit.nl>
