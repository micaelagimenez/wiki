---
layout: default
title:  "Install on UEFI with Encryption"
parent: Install Archcraft with ABIF
nav_order: 1
---

# Install Archcraft On An UEFI System

Follow the steps below to install Archcraft on a UEFI system (with optional encryption).

- After creating a [bootable USB](../../boot/usb), boot system in UEFI mode with it and select <span class="text-blue-100">Boot Archcraft (64bit, UEFI)</span>

![img](../../../assets/images/uefi/1.png)

- On login screen, enter <span class="text-red-300">`liveuser`</span> as the password and login to openbox desktop.

![img](../../../assets/images/bios/2.png)

- Press <span class="label label-green">Window</span> or <span class="label label-green">Alt + F1</span> key to open launcher, select <span class="text-blue-100">Install Archcraft (Expert)</span> and launch installer. Root password is : <span class="text-red-300">`liveuser`</span>

![img](../../../assets/images/bios/3.png)

- Select the language and press <span class="label">Enter</span> You'll see some messages like <span class="text-blue-100">All checks passed!</span>

![img](../../../assets/images/uefi/4.png)

- Each step must be followed in ORDER. Now, select <span class="text-blue-100">Prepare Installation</span> and press <span class="label">Enter</span>

![img](../../../assets/images/uefi/5.png)

- Select <span class="text-blue-100">Set Virtual Console</span> and press <span class="label">Enter</span>

![img](../../../assets/images/uefi/6.png)

- I'm selecting <span class="text-blue-100">US</span>. Choose whichever you prefer and press <span class="label">Enter</span>

![img](../../../assets/images/uefi/7.png)

- Select <span class="text-blue-100">Set Desktop Keyboard Layout</span> and press <span class="label">Enter</span>

![img](../../../assets/images/uefi/8.png)

- Again, whichever you prefer. I'm selecting <span class="text-blue-100">US</span>

![img](../../../assets/images/uefi/9.png)

- Select <span class="text-blue-100">List Devices (optional)</span> and press <span class="label">Enter</span>

![img](../../../assets/images/uefi/10.png)

- Here, you can see a list of devices and partitions on your system. Remember the name of device or partition on which you want to install Archcraft.

![img](../../../assets/images/uefi/11.png)

- Now, go ahead and select <span class="text-blue-100">Partition Disk</span> and press <span class="label">Enter</span>

![img](../../../assets/images/uefi/12.png)

- Select the device/disk you want to partition and press <span class="label">Enter</span> I'm going to install Archcraft on first HD, <span class="text-blue-100">/dev/sda</span>

![img](../../../assets/images/uefi/13.png)

- Select <span class="text-blue-100">gparted</span> and press Enter. You can also use <span class="text-blue-100">parted</span> if you prefer CLI.

![img](../../../assets/images/uefi/14.png)

- I'm installing it on an empty disk, so let's create a partiton table first. Select <span class="text-blue-100">gpt</span> and press <span class="label">Apply</span>

![img](../../../assets/images/uefi/15.png)

- You can create <span class="text-blue-100">root</span>, <span class="text-blue-100">boot</span>, <span class="text-blue-100">home</span> and <span class="text-blue-100">swap</span> partitions. When done partitioning, write the changes and exit gparted.

![img](../../../assets/images/uefi/16.png)

- I've created <span class="text-blue-100">boot</span> and <span class="text-blue-100">root</span> partitions. I need a separate boot partition for UEFI and encryption.

![img](../../../assets/images/uefi/16.png)

- Let's setup encryption. Select <span class="text-blue-100">LUKS Encryption</span> and press <span class="label">Enter</span> If you don't want to use encryption, you can skip these steps jump to Step <span class="text-blue-100">Mount Partitions</span>.

![img](../../../assets/images/uefi/17.png)

- I am selecting <span class="text-blue-100">Automatic LUKS Encryption</span>. Again choice is yours, select whichever you prefer and press <span class="label">Enter</span>

![img](../../../assets/images/uefi/18.png)

- Select root partition and press <span class="label">Enter</span> (In my case it's /dev/sda2)

![img](../../../assets/images/uefi/19.png)

- Set the name for encrypted partition. I choose the default.

![img](../../../assets/images/uefi/20.png)

- Enter the password used to encrypt/decrypt the partition and press <span class="label">Enter</span>

![img](../../../assets/images/uefi/21.png)

- Re-enter the same password and press <span class="label">Enter</span> Wait and ignore any warnings like /run/cryptsetup is missing.

![img](../../../assets/images/uefi/22.png)

- Now the partition is open and ready for mounting. press <span class="label">Enter</span> to exit

![img](../../../assets/images/uefi/23.png)

- Select <span class="text-blue-100">back</span> to exit this screen.

![img](../../../assets/images/uefi/24.png)

- If you want to use LVM, select <span class="text-blue-100">Logical Volume Management</span> and press <span class="label">Enter</span>

![img](../../../assets/images/uefi/25.png)

- Here you can setup LVM settings. I'm skipping this step as I don't want to use it.

![img](../../../assets/images/uefi/26.png)

- Mount the partitions we've created. Select <span class="text-blue-100">Mount Partitions</span> and press <span class="label">Enter</span>

![img](../../../assets/images/uefi/27.png)

- If you've setup encryption, choose <span class="text-blue-100">/dev/mapper/cryptroot</span>, otherwise just select <span class="text-blue-100">/dev/sda2</span> to mount as ROOT and press <span class="label">Enter</span>

![img](../../../assets/images/uefi/28.png)

- Select <span class="text-blue-100">ext4</span> and press <span class="label">Enter</span>

![img](../../../assets/images/uefi/29.png)

- Select <span class="text-blue-100">Yes</span> and press <span class="label">Enter</span>

![img](../../../assets/images/uefi/30.png)

- Press <span class="text-blue-100">Cancel</span> and ignore it. Or, if you know what you're doing, choose what you want.

![img](../../../assets/images/uefi/31.png)

- You'll see <span class="text-blue-100">Mount Successful!</span> message when mounted successfully.

![img](../../../assets/images/uefi/32.png)

- Now, mount swap partition (if you've created any). I'm using a swapfile here.

![img](../../../assets/images/uefi/33.png)

- Enter the size of swap file (must be equal to <span class="text-blue-100">System Memory</span>) and press <span class="label">Enter</span>

![img](../../../assets/images/uefi/34.png)

- Now let's mount the <span class="text-blue-100">UEFI boot</span> partition. Select <span class="text-blue-100">/dev/sda1</span> and press <span class="label">Enter</span>

![img](../../../assets/images/uefi/35.png)

- Select <span class="text-blue-100">/boot</span> and press <span class="label">Enter</span>

![img](../../../assets/images/uefi/36.png)

- You'll see <span class="text-blue-100">Mount Successful!</span> message when mounted successfully.

![img](../../../assets/images/uefi/37.png)

- Select <span class="text-blue-100">Done</span> and press <span class="label">Enter</span>

![img](../../../assets/images/uefi/38.png)

- Select <span class="text-blue-100">Back</span> and move to next step.

![img](../../../assets/images/uefi/39.png)

- Select <span class="text-blue-100">Install Base</span> and press <span class="label">Enter</span>

![img](../../../assets/images/uefi/40.png)

- Select <span class="text-blue-100">Install Base Packages</span> and press <span class="label">Enter</span> It will copy the rootfs to your root partition.

![img](../../../assets/images/uefi/41.png)

- Wait till it finish...

![img](../../../assets/images/uefi/42.png)

- Now, select <span class="text-blue-100">Run Mkinitcpio</span> and press <span class="label">Enter</span>

![img](../../../assets/images/uefi/43.png)

- It'll generate the initramfs and fallback initramfs images.

![img](../../../assets/images/bios/47.png)

- Select <span class="text-blue-100">Install Bootloader</span> and press <span class="label">Enter</span>

![img](../../../assets/images/uefi/44.png)

- Select <span class="text-blue-100">grub</span> (recommended) and press <span class="label">Enter</span> You can choose <span class="text-blue-100">systemd-boot</span> if you want.

![img](../../../assets/images/uefi/45.png)

- Press <span class="label">Enter</span> to set grub as default bootloader.

![img](../../../assets/images/uefi/46.png)

- Go back to the main menu.

![img](../../../assets/images/uefi/48.png)

- Select <span class="text-blue-100">Configure Base</span> and press <span class="label">Enter</span>

![img](../../../assets/images/uefi/49.png)

- Select <span class="text-blue-100">Generate FSTAB</span> and press <span class="label">Enter</span>

![img](../../../assets/images/uefi/50.png)

- Select <span class="text-blue-100">UEFI Part UUID</span> and press <span class="label">Enter</span>

![img](../../../assets/images/uefi/51.png)

- Select <span class="text-blue-100">Set Hostname</span> and press <span class="label">Enter</span>

![img](../../../assets/images/uefi/52.png)

- Enter the hostname (default is archcraft) and press <span class="label">Enter</span>

![img](../../../assets/images/uefi/53.png)

- Select <span class="text-blue-100">Set System Locale</span> and press <span class="label">Enter</span>

![img](../../../assets/images/uefi/54.png)

- I'm selecting <span class="text-blue-100">en_US.UTF-8</span>. Choose the one you want and press <span class="label">Enter</span>

![img](../../../assets/images/uefi/55.png)

- Select <span class="text-blue-100">Set Timezone and Clock</span> and press <span class="label">Enter</span>

![img](../../../assets/images/uefi/56.png)

- Select your continent. Mine's <span class="text-blue-100">Asia</span>

![img](../../../assets/images/uefi/57.png)

- Select the city. Mine's <span class="text-blue-100">Kolkata</span>

![img](../../../assets/images/uefi/58.png)

- Select <span class="text-blue-100">Yes</span> and press <span class="label">Enter</span>

![img](../../../assets/images/uefi/59.png)

- Use <span class="text-blue-100">localtime</span> if you're dualbooting with Windows, otherwise UTC.

![img](../../../assets/images/uefi/60.png)

- Select <span class="text-blue-100">Set Root Password</span> and press <span class="label">Enter</span>

![img](../../../assets/images/uefi/61.png)

- Enter the password for the root account.

![img](../../../assets/images/uefi/62.png)

- Select <span class="text-blue-100">Add New User(s)</span> and press <span class="label">Enter</span> You can create multiple user accounts here.

![img](../../../assets/images/uefi/63.png)

- Type your username, must be lowercase. This will be your regular user account.

![img](../../../assets/images/uefi/64.png)

- Enter the password for the new user.

![img](../../../assets/images/uefi/65.png)

- And a regular user will be created.

![img](../../../assets/images/uefi/66.png)

- Select <span class="text-blue-100">Security and systemd Tweaks</span> and press <span class="label">Enter</span>

![img](../../../assets/images/uefi/67.png)

- Choose whichever tweaks you like. When you're done, hit Back.

![img](../../../assets/images/uefi/68.png)

- Select <span class="text-blue-100">Review Configuration Files</span> and press <span class="label">Enter</span>

![img](../../../assets/images/uefi/69.png)

- Here's a list of all config files you can review and modify.

![img](../../../assets/images/uefi/70.png)

- When you're done reviewing & modifying config files, select <span class="text-blue-100">BACK</span> and press <span class="label">Enter</span>

![img](../../../assets/images/uefi/71.png)

- Finally Select <span class="text-blue-100">Done</span> and press <span class="label">Enter</span>

![img](../../../assets/images/uefi/72.png)

- Select <span class="text-blue-100">Yes</span> & exit the installer.

![img](../../../assets/images/uefi/73.png)

That's it! Archcraft is installed on your system. Reboot the machine & enjoy your new OS.
{: .fs-6 .fw-300 }
