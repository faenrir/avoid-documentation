---
layout: default
title: Create Live ISO
parent: Installation
has_children: false
nav_order: 0
---

# Create Live ISO
{: .no_toc }

## Table of contents
{: .no_toc .text-delta }

1. TOC
{:toc}

---

# GNU/Linux

Every GNU/Linux distro comes pre-installed with [dd](https://en.wikipedia.org/wiki/Dd_(Unix)#:~:text=dd%20is%20a%20command%2Dline,to%20convert%20and%20copy%20files.&text=As%20a%20result%2C%20dd%20can,fixed%20amount%20of%20random%20data.). This tool can be used to create the bootable usb stick from the iso or img file. It can also be used in the same way to flash sd cards for the raspberry pi or other single-board pcs.

- if sets the input file

- of sets the output file

- bs sets the blocksize

```bash
sudo dd if=image.iso of=/dev/sda bs=4M
```

The default block size of dd is 512 bytes, which is pretty small. Newer usb sticks have bigger block sizes, most will support something like 4 MB. This will increase the flash time. 

If the process fails you can always change it to a lower value or leave it completely empty. The small default value should work on any functional usb stick, but it might take a little bit longer to flash the image to the stick.

# macOS

macOS also comes pre-installed with dd, just like GNU/Linux distros. But it functions slightly differently. In this use case you only need to set the blocksize with capitalized letters.

```bash
sudo dd if=image.iso of=/dev/sda BS=4M
```

# Windows

Windows does not come pre-installed with convenient tools like dd. 

One of the best tools to create bootable GNU/Linux ISOs is [rufus](https://rufus.ie/). The GUI program is very simple and easy to use. Just select the iso, choose your usb stick and click on start (no need to set other values).
