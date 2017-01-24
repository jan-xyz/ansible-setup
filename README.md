# About

This play is meant to take a bare machine (in the example a raspberry pi) and
update it to allow ansible provisioning.

# Requirements

* a private key for ansible
* a user with sudo privileges

# Usage

ansiblepublickey = path to the ansible public key you want to use

```
ansible-playbook site.yml --ask-pass --ask-become-pass -u clark-kent --extra-vars ansiblepublickey=/Users/clark-kent/.ssh/id_rsa_ansible.pub
```
