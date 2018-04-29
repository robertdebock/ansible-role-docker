docker
=========

[![Build Status](https://travis-ci.org/robertdebock/ansible-role-docker.svg?branch=master)](https://travis-ci.org/robertdebock/ansible-role-docker)

Have Docker (as provided by distribution) available on your system.

Context
--------
This role is a part of many compatible roles. Have a look at [the documentation of these roles](https://robertdebock.nl/) for further information.

Here is an overview of related roles:
![dependencies](https://raw.githubusercontent.com/robertdebock/robertdebock.github.io/artifacts/docker.png "Dependency")

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

You can use these roles to meet all dependencies.
- robertdebock.bootstrap
- robertdebock.buildtools
- robertdebock.epel
- robertdebock.scl
- robertdebock.python-pip

Download the dependencies by issuing this command:
```
ansible-galaxy install --role-file requirements.yml
```

Compatibility
-------------

This role has been tested against the following distributions and Ansible version:

|distribution|ansible 2.3|ansible 2.4|ansible 2.5|
|------------|-----------|-----------|-----------|
|alpine-3.6|yes|yes|yes|
|alpine-3.7|yes|yes|yes|
|archlinux|yes|yes|yes|
|centos-6|no|no|no|
|centos-7|yes|yes|yes|
|debian-wheezy|no|no|no|
|debian-jessie|yes|yes|yes|
|debian-stretch|yes|yes|yes|
|debian-buster|no|no|no|
|fedora-26|yes|yes|yes|
|fedora-27|yes|yes|yes|
|opensuse-42.2|yes|yes|yes|
|opensuse-42.3|yes|yes|yes|
|ubuntu-artful|yes|yes|yes|
|ubuntu-bionic|yes|yes|yes|

Example Playbook
----------------

```
---
- hosts: servers
  become: yes

  roles:
    - role: robertdebock.bootstrap
    - role: robertdebock.buildtools
    - role: robertdebock.epel
    - role: robertdebock.scl
    - role: robertdebock.python-pip
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

Robert de Bock <robert@meinit.nl>
