# ans_role_config_nfs_client

Install and configure the Network File System (NFS) client.

[![Release](https://img.shields.io/github/release/digimokan/ans_role_config_nfs_client.svg?label=release)](https://github.com/digimokan/ans_role_config_nfs_client/releases/latest "Latest Release Notes")
[![License](https://img.shields.io/badge/license-MIT-blue.svg?label=license)](LICENSE.md "Project License")

## Table Of Contents

* [Purpose](#purpose)
* [Supported Operating Systems](#supported-operating-systems)
* [Quick Start](#quick-start)
    * [Use From Playbook](#use-from-playbook)
* [Role Options](#role-options)
* [Contributing](#contributing)

## Purpose

* Install the [NFS Client](https://en.wikipedia.org/wiki/Network_File_System).
* Configure the NFS Client.

## Supported Operating Systems

* Ubuntu
* Arch Linux
* FreeBSD

## Quick Start

### Use From Playbook

1. Create `requirements.yml` in ansible project root, and add this content:

   ```yaml
   # requirements.yml
   - src: https://github.com/digimokan/ans_role_config_nfs_client
   ```

2. From the project root directory, install/download the role:

   ```shell
   $ ansible-galaxy install --role-file requirements.yml --roles-path ./roles --force-with-deps
   ```

   * _NOTE:_ `--force-with-deps` _ensures subsequent calls download updates_

3. Include the role like any local role, from the project playbook:

   ```yaml
   # playbook.yml
   - hosts: localhost
     connection: local
     tasks:
       - name: "Install and configure the Network File System (NFS) client"
         ansible.builtin.include_role:
           name: ans_role_config_nfs_client
           public: true
         vars:
           nfs_client_nfs_shares_main_mount_dir_path: "/net"
           nfs_client_nfs_share_dirs_root_group: "wheel"
           nfs_client_nfs_shares_to_mount: "{{ my_nfs_shares_list }}"
   ```

## Role Options

Vars with default values, which can be overridden in the playbook:

  * [overridable](../defaults/main/overridable)

Vars defined by this role, exported with `public: true`, for use in other roles:

  * [export](../defaults/main/export/commands.yml)

## Contributing

* Feel free to report a bug or propose a feature by opening a new
  [Issue](https://github.com/digimokan/ans_role_config_nfs_client/issues).
* Follow the project's [Contributing](CONTRIBUTING.md) guidelines.
* Respect the project's [Code Of Conduct](CODE_OF_CONDUCT.md).

