# hname
Print the hostname with time stamp into a file periodically.

## Requirements
- A Linux Ansible host with ansible version 2.8 or above.
- winrm setup on Windows machine for deployment. More information at https://docs.ansible.com/ansible/latest/user_guide/windows_setup.html

## Limitations
- Works on Linux distributions that use systemd.
- On windows, the service fail after n restart attempt could not be configured due the current limitation of ansible module. This is an on going development. See more at https://github.com/ansible/ansible/pull/56445

## Install
Populate the ansible hosts file at /etc/ansible/hosts. A sample hosts file given in this repository.
Seperate ansible playbooks are given for Linux and Windows deployments. Adjust the time period to run the script; the systemd user and Windows user to run the service in the group_vars/all.yml file.

*To store the passwords one can use ansible vault for security issues.*

Clone this repository,

            git clone https://github.com/shahriar52/hname.git
            cd hname

### Linux
For the Linux machines run ansible playbooks as follows:

            ansible-playbook -l linux -i hosts linux.yml -K -b -u <ansible_user>
            
### Windows
For the Windows hosts run ansible playbooks as follows:

            ansible-playbook -l windows -i hosts windows.yml
