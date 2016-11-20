# EfficientIP ansible module
An efficientIP solidserver module for ansible

## Disclaimer

This module is still in heavy developpment.
DO NOT USE IT in production environnement 

## Install

- put it in your Ansible module directory aka "library"
- you also need the "requests" py module

as root (via doas or sudo)

```
pip install requests
```

## Usage
### Task listing...
- ip_space_list
- ip_space_info
- ip_address_add [hostname, IPv4, Space ]
- ip_address_delete [IPv4, Space]

### Or via Playbooke 
```
  tasks:
  - name: list space
    eip:
     ipm_server=10.0.0.4
     ipm_username=ipmadmin
     ipm_password=admin
     ipm_action=ip_space_list
  - name: add IP on space
    eip:
     ipm_server=10.0.0.4
     ipm_username=ipmadmin
     ipm_password=admin
     ipm_action=ip_address_add
     ipm_space=NY_space
     ipm_ip_name=ansible999
     ipm_hostaddr='192.168.1.103'
  - name: properties of a space
    eip:
     ipm_server=10.0.0.4
     ipm_username=ipmadmin
     ipm_password=admin
     ipm_action=ip_space_info
     ipm_space_id=5
  - name: delete IP address
    eip:
     ipm_server=10.0.0.4
     ipm_username=ipmadmin
     ipm_password=admin
     ipm_action=ip_address_delete
     ipm_space=NY_space
     ipm_hostaddr='192.168.1.103'
```
