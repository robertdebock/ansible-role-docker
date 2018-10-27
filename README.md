docker
=========

[![Build Status](https://travis-ci.org/robertdebock/ansible-role-docker.svg?branch=master)](https://travis-ci.org/robertdebock/ansible-role-docker)

Have Docker (as provided by distribution) available on your system.

Context
--------
This role is a part of many compatible roles. Have a look at [the documentation of these roles](https://robertdebock.nl/) for further information.

Here is an overview of related roles:
![dependencies](https://raw.githubusercontent.com/robertdebock/drawings/artifacts/docker.png "Dependency")

Requirements
------------

- Ansible 2.4 or higher.
- Access to a repository containing packages, likely on the internet.
For Red Hat and CentOS systems these packages can be found in epel. Inlcude the role robertdebock.epel to get those repositories.
- docker-py installed by pip. Including the role robertdebock.python_pip is sufficient.
- Alpine, CentOS 7 (not CentOS-6: python and pip are of an old version), Debian, Fedora, openSUSE or Ubuntu.

Role Variables
--------------

None known.

Dependencies
------------

You can use these roles to meet all dependencies.
- [robertdebock.bootstrap](https://travis-ci.org/robertdebock/ansible-role-bootstrap)
- [robertdebock.epel](https://travis-ci.org/robertdebock/ansible-role-epel) (Only for RHEL systems.)
- [robertdebock.python_pip](https://travis-ci.org/robertdebock/ansible-role-python_pip)

Download the dependencies by issuing this command:
```
ansible-galaxy install --role-file requirements.yml
```

Compatibility
-------------

This role has been tested against the following distributions and Ansible version:

distribution|ansible 2.4|ansible 2.5|ansible 2.6|ansible 2.7|ansible devel|
|------------|-----------|-----------|-----------|-----------|-------------|
|alpine-edge*|yes|yes|yes|yes|yes*|
|alpine-latest|yes|yes|yes|yes|yes*|
|archlinux|yes|yes|yes|yes|yes*|
|centos-6|no|no|no|no|no*|
|centos-latest|yes|yes|yes|yes|yes*|
|debian-latest|yes|yes|yes|yes|yes*|
|debian-stable|yes|yes|yes|yes|yes*|
|debian-unstable*|yes|yes|yes|yes|yes*|
|fedora-latest|yes|yes|yes|yes|yes*|
|fedora-rawhide*|yes|yes|yes|yes|yes*|
|opensuse-leap|yes|yes|yes|yes|yes*|
|opensuse-tumbleweed|yes|yes|yes|yes|yes*|
|ubuntu-artful|yes|yes|yes|yes|yes*|
|ubuntu-devel*|yes|yes|yes|yes|yes*|
|ubuntu-latest|yes|yes|yes|yes|yes*|

A single star means the build may fail, it's marked as an experimental build.

Example Playbook
----------------

```
---
- hosts: servers
  become: yes

  roles:
    - role: robertdebock.bootstrap
    - role: robertdebock.epel
    - role: robertdebock.python_pip
    - role: robertdebock.docker

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

[Robert de Bock](https://robertdebock.nl/) <robert@meinit.nl>
