---
layout: default
title:  "Install Archcraft with Calamares"
nav_order: 3
nav_exclude: false
---

# Install Archcraft With Calamares Installer on UEFI/BIOS (With Encryption)

This is a simple guide for beginners and linux newbies to install Archcraft on their system, without messing it up.
Follow the steps below to install Archcraft with Calamares Installer on UEFI or BIOS system (with optional encryption).

I'm assuming that you have already created a [bootable USB](../boot/usb) with Archcraft ISO, boot system with it and
select **Boot Archcraft**. On the login screen, enter <span class="text-red-300">`liveuser`</span> as the password & login to openbox desktop.
Press <span class="label label-green">Window</span> or <span class="label label-green">Alt + F1</span> key to open launcher, select **Install Archcraft** and launch installer.

- You must be on the welcome screen of Archcraft installer now, Select the Installer language & click on <span class="label">Next</span>

![img](../../assets/images/calamares/1.png)

- On the next screen, select your <span class="text-blue-100">Region</span> and <span class="text-blue-100">Time Zone</span>. Installer will do that automatically if you are connected to the internet.

![img](../../assets/images/calamares/2.png)

Here's an important thing to be mentioned, make sure you use an <span class="text-blue-100">UTF-8 System Language</span> or you'll face issues with some programs like (compton, plank, etc). Some programs are not able to detect the windows class and instances with Non UTF-8 system languages.

To check if your selected language is in UTF-8 or not, click on the <span class="label">Change...</span> button at bottom right corner.

![img](../../assets/images/calamares/2a.png)

As you can see, The Indian English, <span class="text-red-100">en_IN</span> is not in UTF-8 format. So I'm going to use <span class="text-blue-100">en_US.UTF-8</span> as the System language.

![img](../../assets/images/calamares/3.png)

Now my system language is set to American English, which is in UTF-8 format. Choose accordingly and click on <span class="label">Next</span> to continue.

![img](../../assets/images/calamares/4.png)

- On the next screen, select your <span class="text-blue-100">Keyboard Layout</span> and click on <span class="label">Next</span>. By default it is automatically set as your system language.

![img](../../assets/images/calamares/5.png)

- Now, It's time to <span class="text-blue-100">Partition the disk</span>. This is where almost every Linux newbie messes things up. <span class="text-red-200">Be careful what you do here</span>.

If you're installing on Virtualbox or any other virtual machine, you can simply choose <span class="text-red-200">Erase disk</span>.
Or If you're trying to dual boot Archcraft with Windows, You can choose <span class="text-red-200">Alongside Windows</span>. It's up to you, how you manage partitioning for your installation.

In this guide, I'm going to install Archcraft on UEFI with Encrypted root partition. I prefer to partition manually, So i'm selecting <span class="text-blue-100">Manual Partitioning</span> and moving forward.

![img](../../assets/images/calamares/6.png)

On the next screen, Click on <span class="label">New Partition Table</span>. This is an empty disk as I'm installing Archcraft on Virtualbox.

![img](../../assets/images/calamares/7.png)

Select <span class="text-blue-100">GUID Partition Table (GPT)</span> If you're booted in UEFI mode. For BIOS, choose <span class="text-blue-100">Master Boot Record (MBR)</span>. You can use GPT for BIOS too, But in that case you have to set up a separate <span class="text-blue-100">BIOS Boot Partition</span>, Or grub will be fail to install.

![img](../../assets/images/calamares/8.png)

Partition table is created, Now click on <span class="label">Create</span> to create partitions...

![img](../../assets/images/calamares/9.png)

Let's make an <span class="text-blue-100">EFI boot partition</span>.
If you are dual booting Archcraft with Windows or Linux, There should already be an EFI boot partition on your disk.
In that case, you don't need to create a new one. Just mount the existing EFI partition at <span class="text-red-100">/boot/efi</span>. Do not format it, otherwise, you won't be able to boot into Windows. 
If you are installing Archcraft with encryption on BIOS, you need to create a separate boot partition as well. 

Here, I've created a 300MB partition for EFI (and for encryption also) and mounted it at <span class="text-red-100">/boot/efi</span> with a <span class="text-blue-100">boot</span> flag.

![img](../../assets/images/calamares/10.png)

Next, I've created a 13GB encrypted btrfs root partition, mounted it at <span class="text-red-100">/</span> with <span class="text-blue-100">root</span> flag.

![img](../../assets/images/calamares/11.png)

And... a swap partition of 2GB, Make sure you make a swap partition or file equal to or bigger than your main memory.

![img](../../assets/images/calamares/12.png)

Here's the partitioning for this installation. You can also create an additional <span class="text-blue-100">/home</span> partition and mount it at /home.
Click on <span class="label">Next</span> to continue the installation. 

![img](../../assets/images/calamares/13.png)

- You may get this message if you choose MBR partition Table on BIOS; Basically the installer wants you to use GPT on BIOS. Just ignore it and click on <span class="label">Ok</span>

![img](../../assets/images/calamares/14.png)

You also may get this warning, if you use encryption and do not encrypt <span class="text-red-100">/boot</span> partition. You can also ignore that or you can go back and encrypt your boot partition as well.

![img](../../assets/images/calamares/15.png)

- Now, Enter your *Name, username, hostname* and *password* and click on <span class="label">Next</span>

![img](../../assets/images/calamares/16.png)

- That's the summary of this installation, Basically everything you did in the installer, Have a good look and then click on <span class="label">Install</span>

![img](../../assets/images/calamares/17.png)

- Now, The actual installation begins. The installer will create partitions, mount them, unpack rootfs, configure locale, generate initrd etc.

![img](../../assets/images/calamares/18.png)

And if connected to the internet, it'll download the package databases then configure the installed system and perform clean up.

![img](../../assets/images/calamares/19.png)

- After successful installation, You can check <span class="text-red-200">Restart now</span> and click on <span class="label">Done</span> to reboot your system.

![img](../../assets/images/calamares/20.png)

That's it! Archcraft is installed on your system. Reboot the machine &amp; enjoy your new OS.
{: .fs-6 .fw-300 }
