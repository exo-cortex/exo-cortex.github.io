---
title: "raspberry_pi_with_arch"
date: 2022-12-25T12:53:11+01:00
draft: true
---

New Raspberry Pi Arch Linux installation

## Prepare sd card

...

## first actions on arch linux

As described [here](https://archlinuxarm.org/platforms/armv8/broadcom/raspberry-pi-4), once logged into the Raspberry Pi change your user to `root` (super user) via the command `su` (default passwort it "root") and enter the commands
```bash
pacman-key --init
pacman-key --populate archlinuxarm
```

### install and enable sudo
See [here](https://wiki.archlinux.org/title/Sudo) for a detailed explanation.
as **root** install `sudo` and `nano` via command `pacman -S sudo`.
Enable your user to use `sudo` by editing `/etc/sudoers` with the command `visudo`. In order to use "nano" as the prepend the command 
```Bash
EDITOR=nano visudo
```
Uncomment the line ```%wheel      ALL=(ALL:ALL) ALL``` to make `sudo` accessable to every user in the group `wheel`.

