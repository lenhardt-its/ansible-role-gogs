# Ansible Role: Gogs

[![ubuntu-18](https://img.shields.io/badge/ubuntu-18.x-orange?style=flat&logo=ubuntu)](https://ubuntu.com/)
[![ubuntu-20](https://img.shields.io/badge/ubuntu-20.x-orange?style=flat&logo=ubuntu)](https://ubuntu.com/)
[![debian-9](https://img.shields.io/badge/debian-9.x-orange?style=flat&logo=debian)](https://www.debian.org/)
[![debian-10](https://img.shields.io/badge/debian-10.x-orange?style=flat&logo=debian)](https://www.debian.org/)
[![centos-7](https://img.shields.io/badge/centos-7.x-orange?style=flat&logo=centos)](https://www.centos.org/)
[![centos-8](https://img.shields.io/badge/centos-8.x-orange?style=flat&logo=centos)](https://www.centos.org/)

[![License](https://img.shields.io/badge/license-MIT%20License-brightgreen.svg?style=flat)](https://opensource.org/licenses/MIT)
[![GitHub issues](https://img.shields.io/github/issues/OnkelDom/ansible-role-gogs?style=flat)](https://github.com/OnkelDom/ansible-role-gogs/issues)
[![GitHub tag](https://img.shields.io/github/tag/OnkelDom/ansible-role-gogs.svg?style=flat)](https://github.com/OnkelDom/ansible-role-gogs/tags)
[![GitHub action](https://github.com/OnkelDom/ansible-role-gogs/workflows/ansible-lint/badge.svg)](https://github.com/OnkelDom/ansible-role-gogs)

## Description

Deploy [Gogs](https://github.com/gogs/gogs) system using ansible.

This is designed to handle services für prometheus service discoery or for gogs template to generate prometheus file_sd files.

## Requirements

- Ansible >= 2.9 (It might work on previous versions, but we cannot guarantee it)

## Role Variables

All variables which can be overridden are stored in [defaults/main.yml](defaults/main.yml) file as well as in table below.

| Name           | Default Value | Description                        |
| -------------- | ------------- | -----------------------------------|
| `proxy_env` |  {} | Set proxy environment variables |
| `gogs_system_user` | gogs | User for Gogs Template |
| `gogs_system_group` | gogs | Group for Gogs Template |
| `gogs_home` | /var/lib/gogs |  |
| `gogs_version` | 0.12.03 |  |
| `gogs_environment` | prod |  |
| `gogs_protocol` | http |  |
| `gogs_root_url` | "git.{{ ansible_domain }}" |  |
| `gogs_secret_key` | "czKH7uDehbwHWyB" |  |
| `gogs_package` | linux_amd64.tar.gz |  |
| `gogs_reverse_proxy` | true |  |
| `gogs_domain` | "{{ ansible_hostname}}.{{ ansible_domain }}" |  |
| `gogs_db_type` | SQLite3 |  |
| `gogs_db_host` | "127.0.0.1:3306" |  |
| `gogs_db_user` | root |  |
| `gogs_db_pass` | default |  |
| `gogs_db_name` | gogs |  |
| `gogs_db_path` | "{{ gogs_home }}/data/gogs.db" |  |
| `gogs_app_name` | "Gogs: A painless self-hosted Git service" |  |
| `gogs_repo_root_path` | "{{ gogs_home }}/gogs-repositories" |  |
| `gogs_hostname` | "{{ hostvars[inventory_hostname]['ansible_default_ipv4']['address'] }}" |  |
| `gogs_http_port` | 3000 |  |
| `gogs_ssh_port` | 22 |  |
| `gogs_log_path` | "{{ gogs_home }}/log" |  |
| `gogs_enable_captcha` | true |  |
| `gogs_connection_retries` | 60 |  |
| `gogs_connection_delay` | 5 |  |
| `gogs_admin_username` | gogs |  |
| `gogs_admin_password` | gogs |  |
| `gogs_admin_fullname` | Gogs Administrator |  |
| `gogs_admin_email` | gogs.admin@gogs.io |  |
| `gogs_users` | {} | see defaults/main.yml |
| `gogs_orgs` | [] |  |
| `gogs_repos` | [] |  |

## Example

### Playbook

```yaml
---
- hosts: all
  roles:
  - onkeldom.gogs
```

## Contributing

See [contributor guideline](CONTRIBUTING.md).

## License

This project is licensed under MIT License. See [LICENSE](/LICENSE) for more details.