php
===

This role installs and configures php (cli, fpm) using [ondrej repo](https://launchpad.net/~ondrej/+archive/ubuntu/php).

Role Variables
--------------

- `php_version`: Version number to install (5.5, 5.6, 7.0, 7.1) (e.g. '7.0')
- `php_options`: List of shared ini directives (default: empty list)
- `php_cli`:  Install php cli or not (default: False)
- `php_cli_options`: List of ini directives for php cli (default: empty list)
- `php_fpm`: Install php fpm or not (default: False)
- `php_fpm_options`: List of ini directives for php fpm (default: empty list)
- `php_fpm_pool_options`: List of ini directives for www pool (default: empty list)
- `php_fpm_user`: User php-fpm will run as (default: 'www-data')
- `php_fpm_group`: Group php-fpm will run as (default: php_fpm_user)
- `php_fpm_init_system`: OS init system. Docker phusion/baseimage uses 'runit'. (default 'upstart')
- `php_mod`: Install apache php module or not (default: False)
- `php_mod_options`: List of ini directives for php mod (default: empty list)
- `php_modules`: List of php modules to install (default: empty list)

Example Playbook
----------------

    - hosts: servers
      roles:
        - {
          role: php,
          php_version: '7.0',
          php_cli: True
        }

License
-------

MIT

[![Build Status](https://travis-ci.org/dpujadas/ansible-role-php.svg?branch=master)](https://travis-ci.org/dpujadas/ansible-role-php)