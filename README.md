Ansible: Opencast Certbot Role
==============================

[![lint](https://github.com/elan-ev/opencast_certbot/actions/workflows/lint.yml/badge.svg)](https://github.com/elan-ev/opencast_certbot/actions/workflows/lint.yml)

This Ansible role configures TLS certificate renewal via certbot for Opencast.

Role Variables
--------------

- `opencast_letsencrypt_email`
  - Email address for Let's Encrypt account (_required_)
  - This is used by Let's Encrypt to send certificate expiration warnings if necessary.
- `opencast_certbot_deploy_hook`
  - Command to run after certbot has updated certificate. The value is optional.
    Already created certificates will not be updated.
- `opencast_certbot_enable_epel`
  - On RedHat system certbot package is living in the EPEL repository. Here you can enable (value: `true`)
    or disable (value: `false`) installation of the `epel-release` package (default: `true`).
    On RedHat installation with Satellite this property can be handy.
  - On Debian based systems this property do nothing.

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
