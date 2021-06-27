---
layout: default
title:  "Post Installation"
nav_order: 4
nav_exclude: false
---

# Things To Do After Installing Archcraft OS
{: .no_toc }

<details open markdown="block">
  <summary>
    Table of contents
  </summary>
  {: .text-delta }
1. TOC
{:toc}
</details>

After installing Archcraft OS, there are few things you should do...

### Update System
Refresh package database and Update your installation.

```bash
$ sudo pacman -Syyu
```

If you get <span class="text-red-200">invalid or corrupted package (PGP signature)</span> error, do...

```bash
$ sudo pacman -S archlinux-keyring
$ sudo pacman-key --populate
```

### Install New Softwares
Install your favorite programs with pacman or yay (AUR).

```bash
$ sudo pacman -S firefox gimp

# Or from AUR

$ yay -S spotify		
```

### Enable OS-PROBER
If grub failed to detect other installed Operating systems, edit the config file and regenerate <span class="text-blue-100">grub.cfg</span> file.

```bash
# Edit /etc/default/grub and uncomment this line
#GRUB_DISABLE_OS_PROBER=false

# Regenerate grub config file
$ sudo grub-mkconfig -o /boot/grub/grub.cfg

# Or... just run
$ sudo update-grub						
```

### Fix Screen Tearing
If you're using an AMD based system and facing screen tearing issue, create a <span class="text-blue-100">xorg.conf</span> file like this -

```bash
# Change to xorg.conf.d dir
$ cd /etc/X11/xorg.conf.d

# Create a conf file
$ sudo touch 20-amdgpu.conf

# Edit the file
$ sudo vim 20-amdgpu.conf

# Paste this in the editor
Section "Device"
     Identifier "AMD"
     Driver "amdgpu"
     Option "TearFree" "true"
EndSection						
```

### Enable Suspend Service
Enable betterlockscreen's suspend service for your user account.

```bash
# Enable betterlockscreen suspend service

$ sudo systemctl enable betterlockscreen@$USER.service						
```

### Fix Polybar Icons
If some icons are not showing in the bar.

```bash
# Run the following script to fix battery and network modules in polybar

$ ~/.config/polybar/fix_modules.sh						
```

### Fix Lockscreen
Fix lockscreen layout on hidpi or low resolution displays.

```bash
# Update the lockscreen

$ betterlockscreen -u /usr/share/backgrounds/wal_10.jpg						
```

### Remove Unnecessary Modules From Initrd
let's say you've installed Archcraft on a machine with Intel GPU. In this case you only need <span class="text-blue-100">i915</span>. Delete other modules from the array and rebuild initrd.

```bash
# Edit mkinitcpio.conf file
$ sudo vim /etc/mkinitcpio.conf

# Change line 7 from
MODULES=(i915? amdgpu? radeon? nouveau? vboxvideo? vmwgfx?)
# To
MODULES=(i915)

# Save file and rebuild initrd
$ sudo mkinitcpio -p linux						
```

Well, that's pretty much everything for now, go ahead and try out Archcraft.
{: .fs-6 .fw-300 }
