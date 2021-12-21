---
title: "how to use arduino on linux"
date: 2021-12-19T18:47:23+01:00
draft: false
tags: [arduino, setup, commandline, bash, compilation]
---


Installing the arduino IDE goes like this:

```bash
$ sudo dnf install arduino
```

On Fedora linux the Arduino appears as a file. 
```bash
ls -l /dev/ttyACM0 
# this returns:
# crw-rw----. 1 root dialout 166, 0 Dec 19 18:43 /dev/ttyACM0 
```
This means the "file" (the file representing the Arduino) is owned by root i.e. only root may manipulate it. In order for your current user to manipulate the Arduino we have to add "username" to the group "dialout":

```bash 
$ sudo usermod -a -G dialout <username>
```

Finally I had to create a directory manually that the arduino IDE was not allowed to create itself.

```bash
$ sudo mkdir /usr/share/arduino/tools-builder
```

Compiling and uploading an arduino-sketch to the board directly from the commandline is also possible:

```bash
$ arduino --upload sketch/sketch.ino --port /dev/ttyUSB*
```