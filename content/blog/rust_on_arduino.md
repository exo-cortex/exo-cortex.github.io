---
title: "rust_on_arduino"
date: 2022-01-08T13:07:22+01:00
draft: true
---

This post shall document my journey of programming/learning to programm my little 10+-year-old Arduino Uno in Rust.

## 1. Installing "rustup" on Fedora-Linux 
I learned that "rustup" is not provided by Fedora's own package manager dnf. So it has to be installed via a script:
```bash
$ curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs | sh
# doesn't need sudo - yay!
```
(rustup also didn't like other dnf-installed rust-tools on my system and asked me to uninstall them.)
see (here)[https://www.linuxcapable.com/how-to-install-rust-programming-language-on-fedora-34-35/] for more information.

## 2. "can I program my arduino with rust?"
asking a friend this question he sent me a link about it: https://dev.to/creativcoder/how-to-run-rust-on-arduino-uno-40c0


## ___ linkdump:

https://github.com/Rahix/avr-hal collection of rust-crates for different arduino boards
