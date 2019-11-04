Ansible Role : Raspberry Pi4 Kubenetes install
=========

This role will install a master and multiple workers joined in a cluster to
Raspberry Pi4s.

Before using the role:

- each pi must have a newly [flashed](https://www.balena.io/etcher/) sd card with [raspbian buster lite](https://www.raspberrypi.org/downloads/raspbian/) from image >= 2019-09-26
- the file /boot/ssh must be created on the first partition of  each sd card to allow ssh login
- the pi should ideally get its ip address from a static DHCP lease
    - if not ip addresses will have to be manually configured using either `sudo raspi-config` or by following an [online guide](https://thepihut.com/blogs/raspberry-pi-tutorials/how-to-give-your-raspberry-pi-a-static-ip-address-update)
- boot the pi from the sd card and perform initial login using login pi:raspberry, adding key to known hosts

Hosts file
----------

An example hosts file is provided in this directory, uncomment and edit for ip
addresses and number of workers.

Example Playbook
----------------

An example playbook `pi-k8s_playbook.yml` is provided in this directory.

To use, run:
```
ansible-playbook pi-k8s_playbook.yml
```

To limit to certain hosts use e.g.
```
ansible-playbook pi-k8s_playbook.yml -l k8s-pi-master
```

License
-------

GPL v3.0

