Stouts.tinc 0.0.0
=================

Ansible role to manage Tinc VPN

#### Variables

```yaml

tinc_enabled: yes                 # The role in enabled
tinc_netname: net                 # Tinc Name of VPN network
tinc_vpn_interface: tun0          # Tinc VPN Interface

# Hostnames to connect
tinc_hosts: []                    

# Host Physical IP
tinc_physical_ip: "{{ansible_eth0.ipv4.address}}"
tinc_ip: 10.0.0.1                 # Tinc VPN IP
tinc_vpn_netmask: 255.255.255.0   # Tinc VPN Netmask
tinc_vpn_cidr_netmask: 32         # Tinc VPN CIDR
```

#### Usage

Add `Stouts.tinc` to your roles and setup your inventory and playbooks.

Example (inventory):
```ini
[vpn]
host1 tinc_ip=10.0.0.10 ansible_ssh_host=11.11.11.11
host2 tinc_ip=10.0.0.10 ansible_ssh_host=11.11.11.11
host3 tinc_ip=10.0.0.10 ansible_ssh_host=11.11.11.11
```

```yaml

- hosts: all

  roles:
  - Stouts.tinc

  vars:
    tinc_physical_ip: "{{ansible_ssh_host}}"
```

#### License

Licensed under the MIT License. See the LICENSE file for details.

#### Feedback, bug-reports, requests, ...

Are [welcome](https://github.com/Stouts/Stouts.tinc/issues)!
