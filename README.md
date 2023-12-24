# Ansible role [node_red](https://galaxy.ansible.com/ui/standalone/roles/buluma/node_red/documentation)

Install and configure Node RED on your system.

|GitHub|Version|Issues|Pull Requests|Downloads|
|------|-------|------|-------------|---------|
|[![github](https://github.com/buluma/ansible-role-node_red/actions/workflows/molecule.yml/badge.svg)](https://github.com/buluma/ansible-role-node_red/actions/workflows/molecule.yml)|[![Version](https://img.shields.io/github/release/buluma/ansible-role-node_red.svg)](https://github.com/buluma/ansible-role-node_red/releases/)|[![Issues](https://img.shields.io/github/issues/buluma/ansible-role-node_red.svg)](https://github.com/buluma/ansible-role-node_red/issues/)|[![PullRequests](https://img.shields.io/github/issues-pr-closed-raw/buluma/ansible-role-node_red.svg)](https://github.com/buluma/ansible-role-node_red/pulls/)|[![Ansible Role](https://img.shields.io/ansible/role/d/buluma/node_red)](https://galaxy.ansible.com/ui/standalone/roles/buluma/node_red/documentation)|

## [Example Playbook](#example-playbook)

This example is taken from [`molecule/default/converge.yml`](https://github.com/buluma/ansible-role-node_red/blob/master/molecule/default/converge.yml) and is tested on each push, pull request and release.

```yaml
---
- name: converge
  hosts: all
  become: yes
  gather_facts: yes

  roles:
    - role: buluma.node_red
```

The machine needs to be prepared. In CI this is done using [`molecule/default/prepare.yml`](https://github.com/buluma/ansible-role-node_red/blob/master/molecule/default/prepare.yml):

```yaml
---
- name: prepare
  hosts: all
  become: yes
  gather_facts: no

  roles:
    - role: buluma.bootstrap
    - role: buluma.ca_certificates
    - role: buluma.epel
    - role: buluma.npm
    - role: buluma.users
      users_group_list:
        - name: nodered
      users_user_list:
        - name: nodered
          group: nodered
```

Also see a [full explanation and example](https://buluma.github.io/how-to-use-these-roles.html) on how to use these roles.

## [Role Variables](#role-variables)

The default values for the variables are set in [`defaults/main.yml`](https://github.com/buluma/ansible-role-node_red/blob/master/defaults/main.yml):

```yaml
---
# defaults file for node_red

# The directory where Node RED should be running from.
node_red_working_directory: /opt/node_red

# The user Node RED should be running under.
# This roles does not create users, see `molecule/default/prepare.yml`.
node_red_user_name: nodered

# The group Node RED should be running under.
# This roles does not create groups, see `molecule/default/prepare.yml`.
node_red_group_name: nodered
```

## [Requirements](#requirements)

- pip packages listed in [requirements.txt](https://github.com/buluma/ansible-role-node_red/blob/master/requirements.txt).

## [State of used roles](#state-of-used-roles)

The following roles are used to prepare a system. You can prepare your system in another way.

| Requirement | GitHub | Version |
|-------------|--------|--------|
|[buluma.bootstrap](https://galaxy.ansible.com/buluma/bootstrap)|[![Ansible Molecule](https://github.com/buluma/ansible-role-bootstrap/actions/workflows/molecule.yml/badge.svg)](https://github.com/buluma/ansible-role-bootstrap/actions/workflows/molecule.yml)|[![Version](https://img.shields.io/github/release/buluma/ansible-role-bootstrap.svg)](https://github.com/shadowwalker/ansible-role-bootstrap)|
|[buluma.ca_certificates](https://galaxy.ansible.com/buluma/ca_certificates)|[![Ansible Molecule](https://github.com/buluma/ansible-role-ca_certificates/actions/workflows/molecule.yml/badge.svg)](https://github.com/buluma/ansible-role-ca_certificates/actions/workflows/molecule.yml)|[![Version](https://img.shields.io/github/release/buluma/ansible-role-ca_certificates.svg)](https://github.com/shadowwalker/ansible-role-ca_certificates)|
|[buluma.epel](https://galaxy.ansible.com/buluma/epel)|[![Ansible Molecule](https://github.com/buluma/ansible-role-epel/actions/workflows/molecule.yml/badge.svg)](https://github.com/buluma/ansible-role-epel/actions/workflows/molecule.yml)|[![Version](https://img.shields.io/github/release/buluma/ansible-role-epel.svg)](https://github.com/shadowwalker/ansible-role-epel)|
|[buluma.npm](https://galaxy.ansible.com/buluma/npm)|[![Ansible Molecule](https://github.com/buluma/ansible-role-npm/actions/workflows/molecule.yml/badge.svg)](https://github.com/buluma/ansible-role-npm/actions/workflows/molecule.yml)|[![Version](https://img.shields.io/github/release/buluma/ansible-role-npm.svg)](https://github.com/shadowwalker/ansible-role-npm)|
|[buluma.service](https://galaxy.ansible.com/buluma/service)|[![Ansible Molecule](https://github.com/buluma/ansible-role-service/actions/workflows/molecule.yml/badge.svg)](https://github.com/buluma/ansible-role-service/actions/workflows/molecule.yml)|[![Version](https://img.shields.io/github/release/buluma/ansible-role-service.svg)](https://github.com/shadowwalker/ansible-role-service)|
|[buluma.users](https://galaxy.ansible.com/buluma/users)|[![Ansible Molecule](https://github.com/buluma/ansible-role-users/actions/workflows/molecule.yml/badge.svg)](https://github.com/buluma/ansible-role-users/actions/workflows/molecule.yml)|[![Version](https://img.shields.io/github/release/buluma/ansible-role-users.svg)](https://github.com/shadowwalker/ansible-role-users)|

## [Context](#context)

This role is a part of many compatible roles. Have a look at [the documentation of these roles](https://buluma.github.io/) for further information.

Here is an overview of related roles:

![dependencies](https://raw.githubusercontent.com/buluma/ansible-role-node_red/png/requirements.png "Dependencies")

## [Compatibility](#compatibility)

This role has been tested on these [container images](https://hub.docker.com/u/buluma):

|container|tags|
|---------|----|
|[Debian](https://hub.docker.com/repository/docker/buluma/debian/general)|bullseye|
|[EL](https://hub.docker.com/repository/docker/buluma/enterpriselinux/general)|8|
|[Fedora](https://hub.docker.com/repository/docker/buluma/fedora/general)|all|
|[Ubuntu](https://hub.docker.com/repository/docker/buluma/ubuntu/general)|focal|
|[Kali](https://hub.docker.com/repository/docker/buluma/kali/general)|all|

The minimum version of Ansible required is 2.12, tests have been done to:

- The previous version.
- The current version.
- The development version.

If you find issues, please register them in [GitHub](https://github.com/buluma/ansible-role-node_red/issues)

## [Changelog](#changelog)

[Role History](https://github.com/buluma/ansible-role-node_red/blob/master/CHANGELOG.md)

## [License](#license)

[Apache-2.0](https://github.com/buluma/ansible-role-node_red/blob/master/LICENSE)

## [Author Information](#author-information)

[Shadow Walker](https://buluma.github.io/)


Template inspired by [Robert de Bock](https://github.com/robertdebock)
