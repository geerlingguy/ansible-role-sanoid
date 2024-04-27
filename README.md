# Ansible Role: Sanoid

[![CI](https://github.com/geerlingguy/ansible-role-sanoid/workflows/CI/badge.svg?event=push)](https://github.com/geerlingguy/ansible-role-sanoid/actions?query=workflow%3ACI)

An Ansible Role that installs Sanoid and Syncoid on Linux servers for ZFS snapshot, backup, and replication management.

## Requirements

ZFS.

## Role Variables

Available variables are listed below, along with default values (see `defaults/main.yml`):

```yaml
TODO
```

## Dependencies

None.

## Example Playbook

Install from the system package manager:

```yaml
    - hosts: zfs
      roles:
        - role: geerlingguy.sanoid
```

## License

GPLv3

## Author Information

This role was created in 2024 by [Jeff Geerling](https://www.jeffgeerling.com/), author of [Ansible for DevOps](https://www.ansiblefordevops.com/).
