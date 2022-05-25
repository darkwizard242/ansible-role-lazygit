[![build-test](https://github.com/darkwizard242/ansible-role-lazygit/workflows/build-and-test/badge.svg?branch=master)](https://github.com/darkwizard242/ansible-role-lazygit/actions?query=workflow%3Abuild-and-test) [![release](https://github.com/darkwizard242/ansible-role-lazygit/workflows/release/badge.svg)](https://github.com/darkwizard242/ansible-role-lazygit/actions?query=workflow%3Arelease) ![Ansible Role](https://img.shields.io/ansible/role/49118?color=dark%20green%20) ![Ansible Role](https://img.shields.io/ansible/role/d/49118?label=role%20downloads) ![Ansible Quality Score](https://img.shields.io/ansible/quality/49118?label=ansible%20quality%20score) [![Quality Gate Status](https://sonarcloud.io/api/project_badges/measure?project=ansible-role-lazygit&metric=alert_status)](https://sonarcloud.io/dashboard?id=ansible-role-lazygit) [![Maintainability Rating](https://sonarcloud.io/api/project_badges/measure?project=ansible-role-lazygit&metric=sqale_rating)](https://sonarcloud.io/dashboard?id=ansible-role-lazygit) [![Reliability Rating](https://sonarcloud.io/api/project_badges/measure?project=ansible-role-lazygit&metric=reliability_rating)](https://sonarcloud.io/dashboard?id=ansible-role-lazygit) [![Security Rating](https://sonarcloud.io/api/project_badges/measure?project=ansible-role-lazygit&metric=security_rating)](https://sonarcloud.io/dashboard?id=ansible-role-lazygit) ![GitHub tag (latest SemVer)](https://img.shields.io/github/tag/darkwizard242/ansible-role-lazygit?label=release) ![GitHub repo size](https://img.shields.io/github/repo-size/darkwizard242/ansible-role-lazygit?color=orange&style=flat-square)

# Ansible Role: lazygit

Role to install (_by default_) [lazygit](https://github.com/jesseduffield/lazygit) on **Debian/Ubuntu** and **EL** systems.

## Requirements

None.

## Role Variables

Available variables are listed below (located in `defaults/main.yml`):

### Variables list:

```yaml
lazygit_app: lazygit
lazygit_version: '0.34'
lazygit_dl_url: https://github.com/jesseduffield/{{ lazygit_app }}/releases/download/v{{ lazygit_version }}/{{ lazygit_app }}_{{ lazygit_version }}_{{ ansible_system }}_{{ ansible_architecture }}.tar.gz
lazygit_bin_path: /usr/local/bin
lazygit_file_owner: root
lazygit_file_group: root
lazygit_file_mode: '0755'
```

### Variables table:

Variable           | Description
------------------ | ---------------------------------------------------------------------------------------------------------------------------------------------------------
lazygit_app        | Defines the app to install i.e. **lazygit**
lazygit_version    | Defined to dynamically fetch the desired version to install. Defaults to: **0.34**
lazygit_dl_url     | Defines URL to download the lazygit binary from.
lazygit_bin_path   | Defined to dynamically set the appropriate path to store lazygit binary into. Defaults to (as generally available on any user's PATH): **/usr/local/bin**
lazygit_file_owner | Owner for the binary file of lazygit.
lazygit_file_group | Group for the binary file of lazygit.
lazygit_file_mode  | Mode for the binary file of lazygit.

## Dependencies

None

## Example Playbook

For default behaviour of role (i.e. installation of **lazygit**) in ansible playbooks.

```yaml
- hosts: servers
  roles:
    - darkwizard242.lazygit
```

For customizing behavior of role (i.e. specifying the desired **lazygit** version) in ansible playbooks.

```yaml
- hosts: servers
  roles:
    - darkwizard242.lazygit
  vars:
    lazygit_version: 0.33
```

For customizing behavior of role (i.e. placing binary of **lazygit** package in different location) in ansible playbooks.

```yaml
- hosts: servers
  roles:
    - darkwizard242.lazygit
  vars:
    lazygit_bin_path: /bin/
```

## License

[MIT](https://github.com/darkwizard242/ansible-role-lazygit/blob/master/LICENSE)

## Author Information

This role was created by [Ali Muhammad](https://www.alimuhammad.dev/).
