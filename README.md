dnsmasq
=========

[![Build Status](https://travis-ci.org/gorbyo/ansible-dnsmasq.svg?branch=master)](https://travis-ci.org/gorbyo/ansible-dnsmasq)

The Role should help setup dnsmasq service as local resolver (without dhcp feature)

Requirements
------------

This role requires Ansible 2.2 or higher and platform requirements are listed in the metadata file.

Role Variables
--------------
  ```
  # Network interface for apply
  mgmt_iface: "{{ansible_default_ipv4.interface}}"

  # List of high level DNS servers (require)
  root_dns:
    - 8.8.8.8
    - 8.8.4.4

  # List local DNS servers and addresses (optional)
  local_dns:
    - { domain: zone1.domain1, ip: "192.168.1.1" }
    - { domain: zone2.domain2, ip: "192.168.2.1" }

  local_hosts:
    - { hostname: host1.zone1.domain1, ip: "192.168.1.1" }
    - { hostname: host2.zone2.domain2, ip: "192.168.2.1" }
  ```
Dependencies
------------

None

Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

    - hosts: servers
      roles:
         - role: gorbyo.dnsmasq
      vars:
        local_dns:
          - { domain: zone1.domain1, ip: "192.168.1.1" }
          - { domain: zone2.domain2, ip: "192.168.2.1" }

        local_hosts:
          - { hostname: host1.zone1.domain1, ip: "192.168.1.1" }
          - { hostname: host2.zone2.domain2, ip: "192.168.2.1" }

License
-------

GPLv2

Author Information
------------------

Oleh Horbachov
