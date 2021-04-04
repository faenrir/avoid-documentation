---
layout: default
title: Installation Guide
parent: Installation
has_children: false
nav_order: 1
---

# Installation Guide
{: .no_toc }

## Table of contents
{: .no_toc .text-delta }

1. TOC
{:toc}

---

# Boot

Boot the machine with the created install medium. UEFI should be used as boot option.

After the boot process you should be greeted with a console based login screen.

Login with:

```
user: root
password: avoid
```

Next we need to check the disks.

```bash
lsblk -d -o +MODEL
```

Remember the NAME of the disk that you want to use for this Linux installation.

Now we can start the installation process! 
Type in avoid-installer and hit enter!

```bash
avoid-installer
```

# Avoid-Installer

## Usage

| Keyboard button | Function |
|------|-----------|
| <kbd>Up</kbd> | Move upwards in the selection menu |
| <kbd>Down</kbd> | Move downwards in the selection menu |
| <kbd>Enter</kbd> | Select an option |
| <kbd>Escape</kbd> | Cancel an option |
| <kbd>Space</kbd> | Mark a list option |

## Keyboard

Select the keymap. The default keymap is qwerty 'us'.

## Hostname

Select a hostname for you computer. This will be your PC's network name.

## Locale

Select your default locale setting. It's advised to use english, because this will also change the language of some terminal outputs and the majority of those will be in english anyway.

## Timezone

Select your timezone.

## Root password

Enter and confirm your root password. The password will not be shown on screen when you type it.

## User account

Create your user account and add it to groups. Do not add the anon group!

Here is a list of advised groups for your main account:

| group | description |
|-------|-------------|
| | |

## Bootloader

Select the disk to install the bootloader on.

In this installation process we will focus on a simple install.

Use the NAME from the lsblk command.

## Partition

Select the same drive as the bootloader. We use cfdisk for partitioning.

### cfdisk usage

| Keyboard button | Function |
|------|-----------|
| <kbd>Up</kbd> | Move upwards in the selection menu |
| <kbd>Down</kbd> | Move downwards in the selection menu |
| <kbd>Left</kbd>/<kbd>Right</kbd> | Select an option |
| <kbd>Enter</kbd> | Use selected option |

Type in partition sizes ending with M (for mb) or G for (gb). 

Leave the input enter to use the rest of the disk.

### partition scheme

| Partition | Filesystem | Size | Description |
|--|--|--|--|
| /dev/sda1 | fat32 | 128M | EFI system partition |
| /dev/sda2 | swap | 512M or higher | Swap partition |
| /dev/sda3 | ext4 | Rest of the disk | Root partition |
