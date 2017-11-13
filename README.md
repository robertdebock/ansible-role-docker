Docker
=========

Have Docker available on your system.

Requirements
------------

Pythons pip should be available. The configured robertdebock.python-pip resolves this dependency.

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
    - robertdebock.docker

  tasks:
    - name: Create a data container
      docker_container:
        name: openssh
        image: robertdebock/docker-centos-openssh
        ports:
        - "2222:22"
```

License
-------

Apache License, Version 2.0

Author Information
------------------

Robert de Bock <robert@meinit.nl>
