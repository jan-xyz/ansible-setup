# Usage



ansible-setup
=========

This play is meant to take a bare machine and update it to allow ansible provisioning.

Initially, you might want to run it as a different user (e.g. clark-kent), since you do not have an ansible user on your machine. After that you can easily maintain the private key of your ansible user and role it as you which or change other aspects of the user.

Example for a first run:
```
ansible-playbook site.yml -i inventory.file --ask-pass --ask-become-pass -u clark-kent --extra-vars ansiblepublickey=/Users/clark-kent/.ssh/id_rsa_ansible.pub
```
If you want to run it against a single host, just use `-i host-with-comma-in-the-end,` and ansible will run just against this host.

Requirements
------------

None

Role Variables
--------------

`ansiblepublickey`: path to the ansible public key you want to use. It defaults to `id_rsa_ansible` in the files directory within the role.


Dependencies
------------

None

Example Playbook
----------------

    - hosts: all
      roles:
         - { role: jan-xyz.ansible-setup, ansiblepublickey: /path/to/key }

License
-------

BSD

Author Information
------------------

Jan Steinke
(jan-steinke.de)
