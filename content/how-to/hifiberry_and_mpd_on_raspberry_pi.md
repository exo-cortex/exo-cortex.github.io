---
title: "hifiberry_and_mpd_on_raspberry_pi"
date: 2021-10-16T14:45:23+02:00
update: 2022-01-10T22:45:00+02:00
draft: false
tags: [raspberry pi, audio, hifiberry]
---

I set up my Raspberry Pi 4 with Arch Linux [^0]. Having totally forgotten how to make it work with the **Hifiberry DAC+ XLR** audio shield I had to google, read and understand everything again. In order to avoid this hassle and not waste so much fucking time again (and hopefully help some lost souls on the internet in the process) I'm writing everything down here.

## enabling the audio-shield

For the [DAC2-Pro XLR](https://www.hifiberry.com/shop/boards/hifiberry-dac2-pro-xlr/) in the "/boot/config.txt" file add the following lines:
```bash
#hifiberry shield DAC+ XLR
dtoverlay=hifiberry-dacplus
device_tree_param=spi=on
```

(If you are using a different audio shield, hifiberry has a list of all the parameters [^1].)

## allowing your user access to the raspberry pi's audio card

Access to the audio-card by default (at least on Arch Linux (ARM)) is allowed only to the root user. If you run any audio-related commands they will fail or return unsatisfying results. For example if you want to list all of the Raspberry Pi's audio devices by running the command

```bash
aplay -l
```
It will not return the expected list of devices.

In order to make it possible for your user (the account that you are logged into) to access the audio devices we have to add the user to the group "audio" by running the command
```
sudo usermod -G audio -a [your username]
```

I had to restart my raspberry pi for the changes to take effect. 
Now you should be able to run commands that make sound through the Hifiberry. 
mpd now suddenly worked after I scratched my head for a day trying everything out.
cheers.

## setting up mpd[^2] as a system service

by setting up mpd 

- [^0]: [archlinuxarm.org](archlinuxarm.org)
- [^1]: https://www.hifiberry.com/docs/software/configuring-linux-3-18-x/
- [^2]: [music player daemon](https://en.wikipedia.org/wiki/Music_Player_Daemon)