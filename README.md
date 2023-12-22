repository_mgmt
=================

A role for deploying and configuring deb software sources list on Debian based distributions using [Ansible](http://www.ansible.com/).


Requirements
------------

Supported targets:

- Ubuntu all
- Debian all


Role Variables
--------------

This roles comes preloaded with almost every available default. You can override each one in your hosts/group vars, in your inventory, or in your play. See the annotated defaults in `defaults/main.yml` for help in configuration. All provided variables start with `deb__`.

- `deb__distribution` - Distribution selected for source software installation. Default to `{{ ansible_distribution }}`. Options are `["Debian", "Ubuntu"]`.
- `deb__release` - Distribution release software suite. Default to `{{ ansible_distribution_release }}`. Can be override for release upgrade for example.
- `deb__backports` - Enable the backports repository. *Only supported on stable distributions*. Default: `false`.
- `deb__updates` - Enable the updates repository. *Only supported on stable distributions*. Default: `false`.
- `deb__security` - Enable the security repository. *Only supported on stable distributions*. Default: `true`.
- `deb__ubuntu_universe` - Enable the universe section of Ubuntu repositories. Default: `true`.
- `deb__ubuntu_multiverse` - Enable the multiverse section of Ubuntu repositories. Default: `true`.
- `deb__clean_sources` - Remove existing sources. Default is false, options are `["distribution", "all"]`. _"distribution"_ clean `/etc/apt/sources.list` whereas _"all"_ clean all `*.list` found files.
- `set_apt_proxy` - Enable to set proxy for apt update. Default: `false`.
- `debian_repos_url` - url of debian repository. Default: `http://deb.debian.org`.
- `ubuntu_repos_url` - url of debian repository. Default: `http://archive.ubuntu.com`.
- `um_repos` - if set to true um repository will add to sources.list. Default: `false` and template(umRepo.list.j2) is commented.



Dependencies
------------

- None

Extra
-----

Callable tasks:

- `update`: Retrieve new list of packages (apt-get update)


Usage
-----


Still to do
-----------
- Add option to add additional repositories (like zabbix)

Changelog
---------
### 1.0

Initial version.

License
-------

GPLv2

Author Information
------------------

Maryam Mayabi <mayabi@um.ac.ir>
