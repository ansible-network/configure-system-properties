Configure_system_properties
----------------------------

Ansible-network user role to configure device system properties. User will be able to configure basic system device properties used to identify the network device which includes device properties for configuring the hostname, domain name and name server values over network_cli connection to connect to network device. More info can be found at https://docs.ansible.com/ansible/2.5/network/index.html#network-guide

Requirements
------------

- Ansible 2.5 or later

Dependencies
------------
- None

Example Playbook
----------------

```
---
- hosts: all
  tasks:
    - name: configure system properties
      import_role:
        name: sys_prop
        tasks_from: config_sys_prop
      vars:
        sys_props:
          - hostname: test-hostname
            domain_name: hostname.com
            name_server: 192.168.1.1
            extensions:
              ios:
                ip_domain_name: test.hostname.com
              eos:
                ip_domain_name: test.hostname.com
              iosxr:
                vrf_name: vrf_1
                vrf_domain: hostname.com

```
License
-------

GPL-3.0

Author Information
------------------

Ansible-Networking-Team
