docker
=========

[![Build Status](https://travis-ci.org/robertdebock/ansible-role-docker.svg?branch=master)](https://travis-ci.org/robertdebock/ansible-role-docker)

Have Docker (as provided by distribution) available on your system.

Requirements
------------

- Ansible 2.2 or higher.
- Access to a repository containing packages, likely on the internet.
For Red Hat and CentOS systems these packages can be found in epel. Inlcude the role robertdebock.epel to get those repositories.
- docker-py installed by pip. Including the role robertdebock.python-pip is sufficient.
- Alpine, CentOS 7 (not CentOS-6: python and pip are of an old version), Debian, Fedora, openSUSE or Ubuntu.

Role Variables
--------------

None known.

Dependencies
------------

robertdebock.python-pip

Download the dependencies by issuing this command:
```
ansible-galaxy install --role-file requirements.yml
```

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

Install this role using `galaxy install robertdebock.docker`.

License
-------

Apache License, Version 2.0

Author Information
------------------

Robert de Bock <robert@meinit.nl>
