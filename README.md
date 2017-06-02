HAProxy
=======
Install and configure HAProxy server.

Requirements
------------
See `meta/main.yml`.

Role Variables
--------------
See `default/main.yml`.

Dependencies
------------
Depends on a role that provides SSL certs if HAProxy is the SSL endpoint, ie `ansible-role-ssl-certs`.

Example Playbook
----------------
Example:
```
- hosts: servers
  roles:
    - ansible-role-ssl-certs
    - haproxy
```

TODO
----
None.

Licence
-------
Licensed under [CC-BY-SA 4.0](https://creativecommons.org/licenses/by-sa/4.0/).

Author Information
------------------
Luis Gracia while at [EMBL-EBI](http://www.ebi.ac.uk/):
- luis.gracia [at] ebi.ac.uk
- GitHub at [luisico](https://github.com/luisico)
- Galaxy at [luisico](https://galaxy.ansible.com/luisico)
