rnodec.haproxy_rke2
=========

This ansible role sets up haproxy, specifically for an rke2 server, to act as a stable frontend for the api server.  Always pass through tls.  

Requirements
------------

Three linux servers.

Role Variables
--------------

If `haproxy_rke2_enabled` is `true` (default is `false`), these variables must be provided:
* `haproxy_rke2_servers`: a list of server names and ips, for example:
```bash
haproxy_rke2_servers:
- name: server1
  address: 10.0.0.1
- name: server2
  address: 10.0.0.2
- name: server3
  address: 10.0.0.3
```


Dependencies
------------

None


Example Playbook
----------------

```bash
---
- hosts: servers

  vars:
    haproxy_rke2_enabled: true 
    haproxy_rke2_servers:
    - name: server1
      address: 10.0.0.1
    - name: server2
      address: 10.0.0.2
    - name: server3
      address: 10.0.0.3

  roles:
  - RnodeC.haproxy_rke2
```

Author Information
------------------

RnodeC - rnodec.io
