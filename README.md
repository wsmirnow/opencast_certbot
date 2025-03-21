Ansible: Opencast Certbot Role
==============================

[![lint](https://github.com/elan-ev/opencast_certbot/actions/workflows/lint.yml/badge.svg)](https://github.com/elan-ev/opencast_certbot/actions/workflows/lint.yml)

This Ansible role configures TLS certificate renewal via certbot for Opencast.

Role Variables
--------------

- `opencast_letsencrypt_email`
    - Email address for Let's Encrypt account (_required_)
	 - This is used by Let's Encrypt to send certificate expiration warnings if necessary.

Dependencies
------------

This role requires `elan.opencast_nginx`.


Example Playbook
----------------

Example of how to configure and use the role:

```yaml
- hosts: servers
  become: true
  roles:
    - role: elan.opencast_certbot
      opencast_letsencrypt_email: admin@example.com
```
