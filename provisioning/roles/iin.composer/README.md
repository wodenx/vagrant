# Ansible Role: Composer

Installs Composer, the PHP Dependency Manager, on any Linux or UNIX system.


## Credits
  Adapted from https://github.com/geerlingguy/ansible-role-composer

## Requirements

`curl` and `php` (version 5.3+) should be installed and working.

## Role Variables

Available variables are listed below, along with default values (see `vars/main.yml`):

    composer_path: /usr/local/bin/composer

The path where composer will be installed and available to your system. Should be in your user's `$PATH` so you can run commands simply with `composer` instead of the full path.

## Dependencies

  - iin.php (Installs PHP).

## Example Playbook

    - hosts: servers
      roles:
        - { role: iin.composer }

After the playbook runs, `composer` will be placed in `/usr/local/bin/composer` (this location is configurable), and will be accessible via normal system accounts.
