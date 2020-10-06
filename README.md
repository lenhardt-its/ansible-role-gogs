Ansible Gogs
=========

An Ansible role to install and manage the gogs git service

https://github.com/gogs/docs-api

Build Status
------------

Passed 07.08.2019

Requirements
------------

None

Role Variables
--------------

You can define every variable.
```
---
gogs_user: git
gogs_user_home: /home/git
gogs_binary_version: 0.11.86
gogs_http_port: 3000
gogs_environment: prod
gogs_protocol: http
gogs_root_url: "git.local.domain"
gogs_secret_key: "hGasdSADFASoiSDasB"
```

Dependencies
------------

None

Example Playbook
----------------
```
- hosts: all
  become: true
  vars:
  roles:
    - role: ansible-gogs
  tasks:
```

License
-------

BSD

Author Information
------------------

Dominik Lenhardt
- https://onkeldom.eu
- dom [at] onkeldom.eu
