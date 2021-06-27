---
layout: default
title: "Create A Bootable USB"
parent: Boot Archcraft
nav_order: 1
---

# Create a bootable Archcraft USB
{: .no_toc }

<details open markdown="block">
  <summary>
    Table of contents
  </summary>
  {: .text-delta }
1. TOC
{:toc}
</details>


## dd (Linux)

If you're already using Linux, you can create an Archcraft bootable USB with **dd**.
dd creates both BIOS and UEFI bootable USB & this method is recommended due to its simplicity and universal availability.
Follow the steps below to create a bootable USB with dd :

- Open a terminal and run `sudo fdisk -l` to get the USB info. In my case, it's **/dev/sda**.

```bash
$ sudo fdisk -l

Disk /dev/sda: 29.25 GiB, 31406948352 bytes, 61341696 sectors
Disk model: Cruzer Blade
Units: sectors of 1 * 512 = 512 bytes
Sector size (logical/physical): 512 bytes / 512 bytes
I/O size (minimum/optimal): 512 bytes / 512 bytes
Disklabel type: dos
Disk identifier: 0x940318b0
```

Or... you can run `lsblk` to get the USB information, based on it's size.

```bash
$ lsblk

NAME        MAJ:MIN RM   SIZE RO TYPE MOUNTPOINTS
sda           8:0    1  29.3G  0 disk
├─sda1        8:1    1   1.6G  0 part
└─sda2        8:2    1    54M  0 part
nvme0n1     259:0    0 238.5G  0 disk
```

- After finding your USB device, Run `dd` to flash the ISO on USB 

```bash
$ sudo dd bs=4M if=path/to/archcraft.iso of=/dev/sdX status=progress oflag=sync
```

- Make sure you replace **path/to/archcraft.iso** with the Archcraft ISO path and **sdX** with your USB device.
- This will create a bootable Archcraft USB for both **BIOS & UEFI**.

## Etcher (Linux, Mac, Windows)

[Etcher](https://www.balena.io/etcher/) is an OS image flasher built with Node.js and Electron, capable of flashing an SDCard or USB drive.
It protects you from accidentally writing to your hard-drives and ensures every byte of data was written correctly.
Follow the steps below to create a bootable USB with Etcher :

1. Launch Etcher. Click on **Select Image** and select the Archcraft ISO.
1. Select your USB drive, **Be careful here** and select the right one.
1. Click on **Flash!** and wait for it to finish.
1. This will create a bootable Archcraft USB for both **BIOS & UEFI**.

## Other Options

### Linux - Command line

1. **With `cat`** : Open a terminal and run -
```bash
$ sudo cat path/to/archcraft.iso > /dev/sdX
```
1. **With `cp`** : Open a terminal and run -
```bash
$ sudo cp path/to/archcraft.iso /dev/sdX
```
1. **With `tee`** : Open a terminal and run -
```bash
$ sudo tee < path/to/archcraft.iso > /dev/sdx
```

Make sure you replace **path/to/archcraft.iso** with the Archcraft ISO path and **sdX** with your USB device.

### Windows - Rufus

[Rufus](https://rufus.akeo.ie/) is a multi-purpose USB ISO writer. It provides a graphical user interface and does not care if the drive is properly formatted or not.
Simply select the Archcraft ISO, the USB drive you want to create the bootable Archcraft onto and click START.

> "If the USB drive does not boot properly using the default ISO Image mode, DD Image mode should be used instead."
{: .text-red-200}

- For Rufus version ≥ 3.0 select GPT from the Partition scheme drop-down menu. After clicking START you will get the mode selection dialog, select DD Image mode.
- For Rufus version < 3.0 select DD Image mode from the drop-down menu on the bottom.

