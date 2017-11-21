# Common

Role to install and configure some basic utilities for a server.

## Requirements

`sudo` and `python`.

## Role Variables

### Docker

* `docker_graph_path`: Base directory for **docker**.
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

None.

## Example playbook

```yaml
- hosts: all
  roles:
    - anarres-common
```

## Testing

To test the role you need [molecule](http://molecule.readthedocs.io/en/latest/)
.

```bash
molecule test
```

## License

GPLv3

## Author Information

m0wer: m0wer (at) autistici.org
