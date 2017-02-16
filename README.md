ansible-olsrd2
==============

[![Galaxy](http://img.shields.io/badge/galaxy-ninuxorg.olsrd2-blue.svg?style=flat-square)](https://galaxy.ansible.com/ninuxorg/olsrd2/)

Automatically install and upgrade olsrd2 on debian based linux distributions via ansible.

Role Variables
--------------

```yaml
# interfaces OLSRd2 will bind to
olsrd2_interfaces:
    - eth0
olsrd2_build_dependencies:
    - build-essential
    - libnl-3-dev
    - cmake
    - git
    - libnl-genl-3-dev
    - libnl-utils
    - pkg-config
    - doxygen
    - devscripts
    - dh-systemd
olsrd2_dir: "/opt/olsrd2"
olsrd2_source_repo: https://github.com/OLSR/OONF.git
olsrd2_source_dir: "{{ olsrd2_dir }}/source"
olsrd2_source_version: HEAD  # master
olsrd2_git_email: "git@{{ ansible_domain }}"
olsrd2_git_name: "{{ ansible_user }}"
```

Example Playbook
----------------

```yaml
- hosts: myserver
  roles:
    - ninux.olsrd2
  vars:
    olsrd2_interfaces:
      - eth0
```
