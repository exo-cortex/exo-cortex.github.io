+++
title = "Remove Orphaned Packages"
date = 2026-05-02
draft = false
slug = "remove-orphaned-packages"

[taxonomies]
tags = ["archlinux", "pacman", "cleanup"]
+++

# How Clean up orphaned packages on arch linux

Use this command to get a list list of unneeded packages and directly remove it with pacman. 

```sh
pacman -Qqtd | sudo pacman -Rns -
```

Explanation:
1. Retrieve packages that were not explicitly installed or were installed as dependencies but dependents were since removed:
  - **Q** - Query
  - **q** - quiet
  - **t** - unrequired
  - **d** - nodeps

2. Remove packagesr recursively without creation of backug config files
  - **R** - Remove
  - **n** - no-save (do not save configs as backups)
  - **s** - recursive
