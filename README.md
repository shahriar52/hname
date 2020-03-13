# hname
Print the hostname with time stamp into a file periodically.

## Pre-requisites
- A Linux Ansible host with ansible version 2.8 or above.
- winrm setup on Windows machine for deployment. More information at https://docs.ansible.com/ansible/latest/user_guide/windows_setup.html

## Limitations
- Works on Linux distribution that uses systemd.
- On windows service fail after n restart attempt could not be configured due the current limitation of ansible module. This is a on going development. See https://github.com/ansible/ansible/pull/56445
