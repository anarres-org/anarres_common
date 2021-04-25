# Anarres common

Ansible role to install and configure some basic utilities for a GNU/Linux
server.

It is part of [anarres](https://github.com/anarres-org/anarres), a playbook that
uses a collection of roles to deploy a full-featured server. But it can be used
and tested independently.

## Compatibility

These are the tested GNU/Linux distributions. Maybe it works on some other
distributions too or just requieres a few changes.

* [Debian](https://www.debian.org/)
  * buster
* [Ubuntu](https://ubuntu.com/)
  * latest

## Requirements

In your local machine:

```bash
pip install -r requirements.txt
```

## Role Variables

### Docker

* `docker_data_root`: Base directory for **docker**.
* `dockerfile_path`: Directory that stores the dockerfiles.
* `docker_registry_mirror`: URL to a **docker** registry mirror.
* `db_docker_image`: Database docker image name and tag.

### SendXMPP

* `sendxmpp_jid`: Jabber ID for sendxmpp to send notifications.
* `sendxmpp_pass`: Password for the JID.
* `sendxmpp_config`: Path to **sendxmpp** configuration file.

### NTP

* `ntp_servers`: List of NTP mirrors.

## Dependencies

`sudo` and `python` in the target host(s).

## Example playbook

```yaml
- hosts: all
  gather_facts: false
  pre_tasks:
    - name: Gather facts
      setup:
        filter: ansible_*
  roles:
    - anarres_common
```

## Testing

To test the role you need [molecule](http://molecule.readthedocs.io/en/latest/),
**vagrant**, **virtualbox** and some python requirements that can be installed wwith
`pip install -r requirements-dev.txt`.

```bash
molecule test
```

or

```bash
make test
```

There is more documentation about the installation and configuration of the
required tools at
[Testing - Anarres documentation](https://anarres-org.github.io/anarres/testing/).

## License

GPLv3

## Author Information

* m0wer (at) autistici (dot) org
