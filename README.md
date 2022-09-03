Firewall Ansible Role
=========

Ansible role to configure common software firewall rules depending on OS. Supports the following firewalls:
- FirewallD
- UFW
- ConfigServer Firewall (CSF)
- Windows Firewall

Requirements
------------

None

Role Variables
--------------

- `firewall_incoming_tcp_ports: []`

Example
```yaml
firewall_incoming_tcp_ports:
 - "22"
 - "6934"
```

- `firewall_incoming_udp_ports: []`

Example
```yaml
firewall_incoming_udp_ports:
 - "53"
```

- `firewall_outgoing_tcp_ports: []`

- `firewall_outgoing_udp_ports: []`

- `firewall_rich_rules: []`

Example
```yaml
firewall_rich_rules:
 - {"family": "ipv4", "source_address": "41.208.72.148/32", "dest_port": "161", "protocol": "udp"}
 - {"family": "ipv4", "source_address": "41.208.72.148/32", "dest_port": "5666", "protocol": "tcp"}
```

Dependencies
------------

None

Example Playbook
----------------

```yaml
    - hosts: servers
      roles:
         - { role: libyanspider.firewall_ansible_role, firewall_incoming_tcp_ports: [22,443] }
```

License
-------

BSD

Author Information
------------------

Ahmed Shibani (#shumbashi)
sheipani@gmail.com
