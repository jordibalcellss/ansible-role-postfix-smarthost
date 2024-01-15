# ansible-role-postfix-smarthost

An Ansible role that installs and configures an authenticated relay with
[Postfix](https://www.postfix.org/) under RHEL.

## Description

Quite often we I find myself not running a suitable email server and would like
to use a relay instead. Its implementation with Postfix can be easily deployed
using Ansible.

The SMTP relay settings can be configured in `vars/main.yml`. The
[Mutt](http://www.mutt.org/) email client is also installed by default and
(at your option) handed over with a `.muttrc` file for establishing default
headers.

The configuration is tested using a handler that runs the `mail` program to
send an email to `test_rcpt`.

Tested under AlmaLinux 9.

## Example playbook

```yaml
---
- hosts: server
  tasks:
  - import_role:
      name: ansible-role-postfix-smarthost
```

## License

This project is licensed under the MIT license - see the LICENSE file for
details.
