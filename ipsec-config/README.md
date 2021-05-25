ipsec-config
=========

configure IPSec on hosts with stongSwan

Requirements
------------

None.

Role Variables
--------------

`ipsec_target_cidr`: IPSec target CIDR block (default: `0.0.0.0/32`)\
`ipsec_source_cidr`: IPSec source CIDR block (default: `0.0.0.0/0`)\
`ipsec_secret`: IPSec Secret (default: `abcd`)

Dependencies
------------

None

Example Playbook
----------------

    - hosts: servers
      tasks:
      - name: install IPSec on servers
        include_role:
          name: ipsec-config

License
-------

BSD

Author Information
------------------

