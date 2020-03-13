# hname
Print the hostname with a timestamp into a file periodically.

## Requirements
- A Linux Ansible host with ansible version 2.8 or above.
- winrm setup on Windows machine for deployment. More information at https://docs.ansible.com/ansible/latest/user_guide/windows_setup.html

## Limitations
- Works on Linux distributions that use systemd.
- On the Windows hosts, the service fails after n restart attempt could not be configured due to the current limitation of the ansible module. This is an ongoing development. See more at https://github.com/ansible/ansible/pull/56445

## Install
Populate the ansible hosts file at /etc/ansible/hosts. A sample hosts file given in this repository.
Separate ansible playbooks are given for Linux and Windows deployments. Adjust the time period to run the script; the systemd user and Windows user to run the service in the group_vars/all.yml file.

Clone this repository,

            git clone https://github.com/shahriar52/hname.git
            cd hname

### Linux
For the Linux machines run ansible playbooks as follows:

            ansible-playbook -l linux -i hosts linux.yml -K -b -u <ansible_user>
            
### Windows
For the Windows hosts run ansible playbooks as follows:

            ansible-playbook -l windows -i hosts windows.yml
