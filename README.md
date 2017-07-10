HAProxy
=======
Install and configure HAProxy server.

Requirements
------------
See `meta/main.yml`.

Role Variables
--------------
All configuration happens in `/etc/haproxy/haproxy.cfg` based on the `haproxy.cfg.j2` template. The template is divided in four sections:
- Defaults: contains the `global` and `main-defaults` for all other sections.
- TCP Proxies: contains the configuration for general tcp proxies combining frontends and backends. These are defined in `haproxy_tcp_listens`
- HTTP Proxies: contains the configuration for http frontend and backends, independently. These are defined in `haproxy_http_frontends` and `haproxy_http_backends`.
- Statistics frontend: configures HAProxy's stats frontend.

See `default/main.yml` for more details on the attributes available for tcp and http proxies, as well as the statistics frontend.

HAProxy can be configured with SSL by passing the appropiate configuration to the proxie, ie:
```
haproxy_http_frontends:
  - name: https
    bind: 0.0.0.0:443 ssl crt {{ssl_certs_combined_path}}
```

In the example above Galaxy role `luisico.ansible-role-ssl-certs` is used to provide the path to the SSL certificate.

Dependencies
------------
Depends on a role that provides SSL certs if HAProxy is the SSL endpoint, ie `luisico.ansible-role-ssl-certs`.

Example Playbook
----------------
Example:
```
- hosts: servers
  roles:
    - luisico.ansible-role-ssl-certs
    - haproxy
```

TODO
----
None.

Licence
-------
Released under the [MIT license](https://opensource.org/licenses/MIT).

Author Information
------------------
Luis Gracia while at [EMBL-EBI](http://www.ebi.ac.uk/):
- luis.gracia [at] ebi.ac.uk
- GitHub at [luisico](https://github.com/luisico)
- Galaxy at [luisico](https://galaxy.ansible.com/luisico)
