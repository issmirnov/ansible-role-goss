# Ansible Role: Goss

Installs the [goss](https://github.com/aelsabbahy/goss) binary and runs the
tests specified. Uses [indusbox/goss-ansible](https://github.com/indusbox/goss-ansible)
driver, which must be installed to ansible's library path.

## Sample Playbook

```
- name: run asserts to check something
  hosts: all
  vars:
    goss_payload:
      file:
        /usr/local/bin/zsh:
          exists: true
          mode: "0755"
      package:
        zsh:
          installed: false
  roles:
    - ansible-role-goss

```
