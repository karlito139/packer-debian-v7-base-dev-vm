# packer-debian-v7-base-dev-vm

## Description

Packer template for generating a base Debian v7 VM image.

This is the base Debian v7 VM we use for __[Scrapum](http://scrapum.com "Scrapum")__. We have another private Packer template which further configures and provisions the base VM image generated from this template.

## Prerequisites

 - [Packer](http://packer.io "Packer")
 - [VirtualBox](http://virtualbox.org "Oracle VM VirtualBox")

## Installation and usage

```sh
git clone https://github.com/scrapum/packer-debian-v7-base-dev-vm.git PATH
cd PATH
packer build template.json # Let it run solo to do its magic.
```

### Variables

The following are several variables you can _[change](http://packer.io/docs/templates/user-variables.html "User Variables in Templates - Packer")_ for this template.

 - `vm_debian_packages_to_install` (default: `"automake bison build-essential curl emacs fish flex g++ git libgdbm-dev libncurses5-dev libreadline-dev libssl-dev llvm-dev mosh nfs-common nfs-kernel-server portmap python-software-properties sed subversion tar tig tmux tree unzip vim wget zlib1g-dev"`)
 - `vm_domain_name` (default: `"terminator.dev"`)
 - `vm_hostname` (default: `"terminator"`)
 - `vm_keymap` (default: `"us"`)
 - `vm_locale` (default: `"en_US"`)
 - `vm_user_full_name` (default: `"The Terminator Commander"`)
 - `vm_user_password` (default: `"beawesome"`)
 - `vm_user_username` (default: `"commander"`)

Feel free to take a look at __template.json__ to see these variables in action.

## Known issues

Packer automates the VM creation process by sending scancodes to the VM via `boot_command`. Depending on your machine's specs and performance, this process may or may not work well for you as waiting times may differ drastically (a command that might take 1 second on our machines could take 10 seconds on yours). This isn't something we can fix. We can only guarantee it works on our machines.

## TODO

You [tell me](https://github.com/scrapum/packer-debian-v7-base-dev-vm/issues "Issues · scrapum/packer-debian-v7-base-dev-vm")!

## Contributors

__[Jonathan Barronville](mailto:jonathan@scrapum.com "jonathan@scrapum.com")__

## License

See "__LICENSE__".
