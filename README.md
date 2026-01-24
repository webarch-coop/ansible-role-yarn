# Webarchitects Yarn Classic Ansible Role

[![pipeline status](https://git.coop/webarch/yarn/badges/master/pipeline.svg)](https://git.coop/webarch/yarn/-/commits/master)

This repository contains an Ansible role for installing [Yarn Classic](https://classic.yarnpkg.com/en/) on Debian Bookworm (12) and older using the `.deb` package.

On Debian Trixie (13) and newer the Yarn Classic package is removed and [node-corepack](https://packages.debian.org/trixie/node-corepack) is installed:

> Corepack is a zero-runtime-dependency Node.js script that acts as a bridge between Node.js projects and the package managers they are intended to be used with during development. In practical terms, Corepack lets you use Yarn, npm, and pnpm without having to install them.

## Role variables

See the [defaults/main.yml](defaults/main.yml) file for the default variables, the [vars/main.yml](vars/main.yml) file for the preset variables and the [meta/argument_specs.yml](meta/argument_specs.yml) file for the variable specification.

The [Webarchitects apt role](https://git.coop/webarch/apt) is included by this role to set the `ansible_local.bash.path`, `ansible_local.dpkg.arch` and `ansible_local.gpg.version` variables.

### yarn

Set the `yarn` variable to `true` run the tasks in this role, it defaults to `false`.

## Repository

The primary URL of this repo is [`https://git.coop/webarch/yarn`](https://git.coop/webarch/yarn) however it is also [mirrored to GitHub](https://github.com/webarch-coop/ansible-role-yarn) and [available via Ansible Galaxy](https://galaxy.ansible.com/chriscroome/yarn).

If you use this role please use a tagged release, see [the release notes](https://git.coop/webarch/yarn/-/releases).

## Copyright

Copyright 2019-2026 Chris Croome, &lt;[chris@webarchitects.co.uk](mailto:chris@webarchitects.co.uk)&gt;.

This role is released under [the same terms as Ansible itself](https://github.com/ansible/ansible/blob/devel/COPYING), the [GNU GPLv3](LICENSE).
