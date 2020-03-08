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
    - issmirnov.goss
```

## Debugging

If you see this error, it means you didn't install the [goss.py](https://github.com/indusbox/goss-ansible/blob/master/goss.py) 
into your ansible library path

```
ERROR! no action detected in task. This often indicates a misspelled module name, or incorrect module path.
```

You can create a folder called `library` in the same path as your playbook, or add an `ansible.cfg` 
and set the `defaults.libary` param to point to your library folder.
