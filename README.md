Ansible Role: dnsmasq
=========

An Ansible role for configuring dnsmasq

Requirements
------------

None

Role Variables
--------------
### System Variables
|Variable|Default|Description|
|---|---|---|
|dnsmasq_port|*undefined*|port to listen on|
|dnsmasq_listen_address|*undefined*|address to listen on|
|dnsmasq_bind_interfaces|false|set to true if you don't want dnsmasq to bind to the wildcard address| 

### DNS Variables
|Variable|Default|Description|
|---|---|---|
|dnsmasq_domain_needed|false|set to true to never forward plain names (names without a domain)|
|dnsmasq_bogus_priv|false|set to true to never forward addresses in the no-routed address space|
|dnsmasq_filterwin2k|false|set to true to filter useless windows-originated DNS requests|
|dnsmasq_resolv_file|*undefined*|set this variable to get upstream dns servers from a file other than /etc/resolv.conf|
|dnsmasq_resolv_strict_order|false|set to true to force dnsmasq to query each server strictly in the order they appear in /etc/resolv.conf|
|dnsmasq_resolv_no_resolv|false|set to true if you don't want dnsmasq to read /etc/resolv.conf|
|dnsmasq_resolv_no_poll|false|set to true if you don't want dnsmasq to poll /etc/resolv.conf|
|dnsmasq_name_servers|*undefined*|a list of upstream name servers (with domain specs)|
|dnsmasq_hosts_no_hosts|false|set to true if you don't want dnsmasq to read /etc/hosts|
|dnsmasq_hosts_addn_hosts|*undefined*|additional hosts file|
|dnsmasq_cache_size|*undefined*|set the dns cachesize|
|dnsmasq_cache_min_ttl|*undefined*|minimum cache TTL|

### DHCP Variables
DHCP configuration is not currently supported

Dependencies
------------

None

Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

    - hosts: servers
      vars:
        dnsmasq_resolv_no_resolv: true
        dnsmasq_resolv_no_poll: true
        dnsmasq_name_servers:
          - 8.8.8.8
          - 8.8.4.4
      roles:
         - dataraven.dnsmasq

License
-------

BSD 3-Clause License

Author Information
------------------

Ben Albon - ben@dataraven.co.uk
