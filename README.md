Role Name
=========

An ansible role for installing and configuring Pound. The primary focus of this role is to use Pound as an SSL frontend for varnish.

Requirements
------------

EPEL repository is required and is installed by the common role.

Role Variables
--------------

| Variable                              | Default                       | Notes				|
| :---                                  | :---                          | :---				|
| pound_enable_http			| false				| 				|
| pound_enable_https			| true				|				|
| pound_http_port			| 80				|				|
| pound_https_port			| 443				|				|
| pound_open_http_port			| false				|				|
| pound_open_https_port			| false				|				|
| pound_http_address			| 0.0.0.0			|				|
| pound_https_address			| 0.0.0.0			|				|
| pound_cert				| /etc/pki/tls/certs/pound.pem	|				|
| pound_ciphers				| "EECDH+ECDSA+AESGCM EECDH+aRSA+AESGCM EECDH+ECDSA+SHA384 EECDH+ECDSA+SHA256 EECDH+aRSA+SHA384 EECDH+aRSA+SHA256 EECDH+AESGCM EECDH EDH+AESGCM EDH+aRSA HIGH !MEDIUM !LOW !aNULL !eNULL !LOW !RC4 !MD5 !EXP !PSK !SRP !DSS" | |

#### Complex variables

    pound_backends:
      - address: x.x.x.1
        port: 80
      - address: x.x.x.2
        port: 80

**Defaults:**

    pound_backends:
      - address: 127.0.0.1
        port: 80

Dependencies
------------

* common

Example Playbook
----------------

    - hosts: servers
      roles:
         - { role: pound }

License
-------

MIT

Author Information
------------------

* [Joshua Rusch](https://correct.horse/)
