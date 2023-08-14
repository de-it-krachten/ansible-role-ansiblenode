[![CI](https://github.com/de-it-krachten/ansible-role-ansiblenode/workflows/CI/badge.svg?event=push)](https://github.com/de-it-krachten/ansible-role-ansiblenode/actions?query=workflow%3ACI)


# ansible-role-ansiblenode

Role for setting up system as Ansible managed node



## Dependencies

#### Roles
- deitkrachten.epel
- deitkrachten.python

#### Collections
- community.general

## Platforms

Supported platforms

- Red Hat Enterprise Linux 7<sup>1</sup>
- Red Hat Enterprise Linux 8<sup>1</sup>
- Red Hat Enterprise Linux 9<sup>1</sup>
- CentOS 7<sup>1</sup>
- RockyLinux 8
- RockyLinux 9
- OracleLinux 8
- OracleLinux 9
- AlmaLinux 8
- AlmaLinux 9
- SUSE Linux Enterprise 15<sup>1</sup>
- openSUSE Leap 15
- Debian 10 (Buster)<sup>1</sup>
- Debian 11 (Bullseye)
- Debian 12 (Bookworm)
- Ubuntu 20.04 LTS
- Ubuntu 22.04 LTS
- Fedora 37
- Fedora 38

Note:
<sup>1</sup> : no automated testing is performed on these platforms

## Role Variables
### defaults/main.yml
<pre><code>
# Install pre-requisits for ansible managed node
ansiblenode_install_prereqs: false

# ansible user
ansiblenode_user_name: ansible

# Ansible group
ansiblenode_group_name: ansible

# Ansible users home directory
ansiblenode_user_home: /home/{{ ansiblenode_user_name }}

# Ansible user shell
ansiblenode_shell: /bin/bash

# Set-up sudo for ansible user
ansiblenode_sudo: true
ansiblenode_sudo_passwordless: true

# List of SSH public keys to allow access
ansiblenode_pubkeys: []
</pre></code>




## Example Playbook
### molecule/default/converge.yml
<pre><code>
- name: sample playbook for role 'ansiblenode'
  hosts: all
  become: "yes"
  vars:
    ansiblenode_install_prereqs: True
  tasks:
    - name: Include role 'ansiblenode'
      ansible.builtin.include_role:
        name: ansiblenode
</pre></code>
