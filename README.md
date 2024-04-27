# Ansible Role: Sanoid

[![CI](https://github.com/geerlingguy/ansible-role-sanoid/workflows/CI/badge.svg?event=push)](https://github.com/geerlingguy/ansible-role-sanoid/actions?query=workflow%3ACI)

An Ansible Role that installs [Sanoid and Syncoid](https://github.com/jimsalterjrs/sanoid) on Linux servers for ZFS snapshot, backup, and replication management.

## Requirements

ZFS.

## Role Variables

Available variables are listed below, along with default values (see `defaults/main.yml`):

```yaml
sanoid_conf: ""
```

The configuration to be stored inside `/etc/sanoid/sanoid.conf`. See the Sanoid project's [README file](https://github.com/jimsalterjrs/sanoid/blob/master/README.md) and [Wiki](https://github.com/jimsalterjrs/sanoid/wiki/Sanoid#options) for examples.

## Dependencies

None.

## Example Playbook

Install from the system package manager:

```yaml
    - hosts: zfs

      vars:
        # This assumes you have a ZFS volume `tank/volume`.
        sanoid_conf: >
          # Filesystem Backups
          [tank/volume]
            use_template = production
            recursive = yes

          # Templates
          [template_production]
            frequently = 0
            hourly = 24
            daily = 30
            monthly = 3
            yearly = 0
            autosnap = yes
            autoprune = yes

      roles:
        - role: geerlingguy.sanoid
```

## License

GPLv3

## Author Information

This role was created in 2024 by [Jeff Geerling](https://www.jeffgeerling.com/), author of [Ansible for DevOps](https://www.ansiblefordevops.com/).
