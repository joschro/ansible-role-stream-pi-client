stream-pi-client
================

Install Stream-Pi client on a Raspberry Pi.

Requirements
------------

1. A Raspberry Pi with RaspiOS (including graphical desktop environment) installed.
2. An Adafruit touchscreen display like this installed: https://learn.adafruit.com/adafruit-pitft-28-inch-resistive-touchscreen-display-raspberry-pi

Role Variables
--------------

A description of the settable variables for this role should go here, including any variables that are in defaults/main.yml, vars/main.yml, and any variables that can/should be set via parameters to the role. Any variables that are read from other roles and/or the global scope (ie. hostvars, group vars, etc.) should be mentioned here as well.

Dependencies
------------

This Playbook uses the following roles from Ansible Galaxy:
  - joschro.pitft
  - joschro.streampi-client

Example Playbook
----------------

Create a playbook file (e.g. ansible-playbook-stream-pi-client.yml) with the following content on the Raspberry Pi you want to make a Stream-Pi after successful RaspiOS installation:
```
---
# Ansible Playbook to set up a Raspberry Pi to be used as a Stream-Pi
- name: Set up a stream-pi client
  hosts: localhost
  gather_facts: no
  roles:
    - { role: joschro.pitft }
```
Create a requirements.yml file in the same directory:
```
# Install a role from the Ansible Galaxy
#- src: joschro.pitft

# Install a role from GitHub
- name: joschro.pitft
  src: https://github.com/joschro/ansible-role-pitft
```

You can now run the two commands on the command line to run the installation:
```
ansible-galaxy install -r requirements.yml --force
ansible-playbook -i localhost ansible-playbook-stream-pi-client.yml
```

License
-------

GPLv3

Author Information
------------------

joschro
