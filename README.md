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
packer build template.json
```

### Variables

The following are several variables you can _[change](http://packer.io/docs/templates/user-variables.html "User Variables in Templates - Packer")_ for this template.

 - `vm_domain_name` (default: `"terminator.dev"`)
 - `vm_full_name` (default: `"Terminator Commander"`)
 - `vm_fs_partition_size_home` (default: `"4 GB"`)
 - `vm_fs_partition_size_root` (default: `"2 GB"`)
 - `vm_fs_partition_size_swap` (default: `"2.5 GB"`)
 - `vm_fs_partition_size_tmp` (default: `"2 GB"`)
 - `vm_fs_partition_size_usr` (default: `"10 GB"`)
 - `vm_fs_partition_size_var` (default: `"max"`)
 - `vm_hostname` (default: `"terminator"`)
 - `vm_password` (default: `"beawesome"`)
 - `vm_username` (default: `"commander"`)

Feel free to take a look at __template.json__ to see these variables in action.

## Known issues

Packer automates the VM creation process by sending scancodes to the VM via `boot_command`. Depending on your machine's specs and performance, this process may or may not work well for you as waiting times may differ drastically (a command that might take 1 second on our machines could take 10 seconds on yours). This isn't something we can fix. We can only guarantee it works on our machines.

## TODO

 - Switch to using a completely command-based approach (related: _[Debian GNU/Linux Installation Guide](http://debian.org/releases/stable/amd64/install.txt.en "Debian GNU/Linux Installation Guide")_).

## Contributors

__[Jonathan Barronville](mailto:jonathan@scrapum.com "jonathan@scrapum.com")__

## License

See "__LICENSE__".
