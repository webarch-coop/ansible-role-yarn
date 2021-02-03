# Ansible Debian Yarn Role 

This repository contains an Ansible role for installing [Yarn Classic](https://classic.yarnpkg.com/en/) on Debian servers using the `.deb` package.

To use this role you need to use Ansible Galaxy to install it into another repository under `galaxy/roles/yarn` by adding a `requirements.yml` file in that repo that contains:

```yml
---
- name: yarn
  src: https://git.coop/webarch/yarn.git
  version: master
  scm: git
```

And a `ansible.cfg` that contains:

```
[defaults]
retry_files_enabled = False
pipelining = True
inventory = hosts.yml
roles_path = galaxy/roles

```

And a `.gitignore` containing:

```
roles/galaxy
```

To pull this repo in run:

```bash
ansible-galaxy install -r requirements.yml --force 
```

The other repo should also contain a `yarn.yml` file that contains:

```yml
---
- name: Install Yarn
  become: yes

  hosts:
    - stretch_servers

  roles:
    - yarn
```

And a `hosts.yml` file that contains lists of servers, for example:

```yml
---
all:
  children:
    stretch_servers:
      hosts:
        host3.example.org:
        host4.example.org:
        cloud.example.com:
        cloud.example.org:
        cloud.example.net:
```

Then it can be run as follows:

```bash
ansible-playbook yarn.yml 
```
