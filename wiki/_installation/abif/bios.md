---
layout: default
title:  "Install on BIOS with Encryption"
parent: Install Archcraft with ABIF
nav_order: 1
---

# Install Archcraft On A BIOS System

Follow the steps below to install Archcraft on a BIOS system (with optional encryption).

- After creating a [bootable USB](../../boot/usb), boot system with it and select <span class="text-blue-100">Boot Archcraft (64bit, BIOS)</span>

![img](../../../assets/images//bios/1.png)

- On login screen, enter <span class="text-red-300">`liveuser`</span> as the password and login to openbox desktop.

![img](../../../assets/images//bios/2.png)

- Press <span class="label label-green">Window</span> or <span class="label label-green">Alt + F1</span> key to open launcher, select <span class="text-blue-100">Install Archcraft (Expert)</span> and launch installer. Root password is : <span class="text-red-300">`liveuser`</span>

![img](../../../assets/images//bios/3.png)

- Select the language and press <span class="label">Enter</span> You'll see some messages like <span class="text-blue-100">All checks passed!</span>

![img](../../../assets/images//bios/4.png)

- Each step must be followed in ORDER. Now, select <span class="text-blue-100">Prepare Installation</span> and press <span class="label">Enter</span>

![img](../../../assets/images//bios/5.png)

- Select <span class="text-blue-100">Set Virtual Console</span> and press <span class="label">Enter</span>

![img](../../../assets/images//bios/6.png)

- I'm selecting <span class="text-blue-100">US</span>. Choose whichever you prefer and press <span class="label">Enter</span>

![img](../../../assets/images//bios/7.png)

- Select <span class="text-blue-100">Set Desktop Keyboard Layout</span> and press <span class="label">Enter</span>

![img](../../../assets/images//bios/8.png)

- Again, whichever you prefer. I'm selecting <span class="text-blue-100">US</span>

![img](../../../assets/images//bios/9.png)

- Select <span class="text-blue-100">List Devices (optional)</span> and press <span class="label">Enter</span>

![img](../../../assets/images//bios/10.png)

- Here, you can see a list of devices and partitions on your system. Remember the name of device or partition on which you want to install Archcraft.

![img](../../../assets/images//bios/11.png)

- Now, go ahead and select <span class="text-blue-100">Partition Disk</span> and press <span class="label">Enter</span>

![img](../../../assets/images//bios/12.png)

- Select the device/disk you want to partition and press <span class="label">Enter</span> I'm going to install Archcraft on first HD, <span class="text-blue-100">/dev/sda</span>

![img](../../../assets/images//bios/13.png)

- Select <span class="text-blue-100">cfdisk</span> and press <span class="label">Enter</span> You can also use <span class="text-blue-100">gparted</span> if you prefer GUI

![img](../../../assets/images//bios/14.png)

- I'm installing it on an empty disk, so let's create a partiton table first. Select <span class="text-blue-100">dos</span> and press <span class="label">Enter</span>

![img](../../../assets/images//bios/15.png)

- You can create <span class="text-blue-100">root</span>, <span class="text-blue-100">boot</span>, <span class="text-blue-100">home</span> and <span class="text-blue-100">swap</span> partitions. When done partitioning, write the changes.

![img](../../../assets/images//bios/16.png)

- I've created <span class="text-blue-100">boot</span> and <span class="text-blue-100">root</span> partitions. I'm going to use encryption, that's why I need a separate boot partition.

![img](../../../assets/images//bios/17.png)

- Let's setup encryption. Select <span class="text-blue-100">LUKS Encryption</span> and press <span class="label">Enter</span> If you don't want to use encryption, you can skip these steps jump to Step <span class="text-blue-100">Mount Partitions</span>.

![img](../../../assets/images//bios/18.png)

- I am selecting <span class="text-blue-100">Automatic LUKS Encryption</span>. Again choice is yours, select whichever you prefer and press <span class="label">Enter</span>

![img](../../../assets/images//bios/19.png)

- Select root partition and press <span class="label">Enter</span> (In my case it's /dev/sda2)

![img](../../../assets/images//bios/20.png)

- Set the name for encrypted partition. I choose the default.

![img](../../../assets/images//bios/21.png)

- Enter the password used to encrypt/decrypt the partition and press <span class="label">Enter</span>

![img](../../../assets/images//bios/22.png)

- Re-enter the same password and press <span class="label">Enter</span> Wait and ignore any warnings like /run/cryptsetup is missing.

![img](../../../assets/images//bios/23.png)

- Now the partition is open and ready for mounting. press <span class="label">Enter</span> to exit

![img](../../../assets/images//bios/24.png)

- Select <span class="text-blue-100">back</span> to exit this screen.

![img](../../../assets/images//bios/25.png)

- If you want to use LVM, select <span class="text-blue-100">Logical Volume Management</span> and press <span class="label">Enter</span>

![img](../../../assets/images//bios/26.png)

- Here you can setup LVM settings. I'm skipping this step as I don't want to use it.

![img](../../../assets/images//bios/27.png)

- Mount the partitions we've created. Select <span class="text-blue-100">Mount Partitions</span> and press <span class="label">Enter</span>

![img](../../../assets/images//bios/28.png)

- If you've setup encryption, choose <span class="text-blue-100">/dev/mapper/cryptroot</span>, otherwise just select <span class="text-blue-100">/dev/sda2</span> to mount as ROOT and press <span class="label">Enter</span>

![img](../../../assets/images//bios/29.png)

- Select <span class="text-blue-100">ext4</span> and press <span class="label">Enter</span>

![img](../../../assets/images//bios/30.png)

- Select <span class="text-blue-100">Yes</span> and press <span class="label">Enter</span>

![img](../../../assets/images//bios/31.png)

- Press <span class="text-blue-100">Cancel</span> and ignore it. Or, if you know what you're doing, choose what you want.

![img](../../../assets/images//bios/32.png)

- You'll see <span class="text-blue-100">Mount Successful!</span> message when mounted successfully.

![img](../../../assets/images//bios/33.png)

- Now, mount swap partition (if you've created any). I'm using a swapfile here.

![img](../../../assets/images//bios/34.png)

- Enter the size of swap file (must be equal to <span class="text-blue-100">System Memory</span>) and press <span class="label">Enter</span>

![img](../../../assets/images//bios/35.png)

- Now let's mount the boot partition. If you haven't created one, just use Done and move to Installation. Otherwise select it ("/dev/sda1" in my case) and press <span class="label">Enter</span>

![img](../../../assets/images//bios/36.png)

- Select <span class="text-blue-100">ext4</span> and press <span class="label">Enter</span>

![img](../../../assets/images//bios/37.png)

- Select <span class="text-blue-100">Yes</span> and press <span class="label">Enter</span>

![img](../../../assets/images//bios/38.png)

- Type <span class="text-blue-100">/boot</span> and press <span class="label">Enter</span> If you've created a separate home partition, you can mount it this way.

![img](../../../assets/images//bios/39.png)

- Again, ignore that.

![img](../../../assets/images//bios/40.png)

- Select <span class="text-blue-100">Done</span> and press <span class="label">Enter</span>

![img](../../../assets/images//bios/41.png)

- Select <span class="text-blue-100">Back</span> and move to next step.

![img](../../../assets/images//bios/42.png)

- Select <span class="text-blue-100">Install Base</span> and press <span class="label">Enter</span>

![img](../../../assets/images//bios/43.png)

- Select <span class="text-blue-100">Install Base Packages</span> and press <span class="label">Enter</span> It will copy the rootfs to your root partition.

![img](../../../assets/images//bios/44.png)

- Wait till it finish...

![img](../../../assets/images//bios/45.png)

- Now, select <span class="text-blue-100">Run Mkinitcpio</span> and press <span class="label">Enter</span>

![img](../../../assets/images//bios/46.png)

- It'll generate the initramfs and fallback initramfs images.

![img](../../../assets/images//bios/47.png)

- Select <span class="text-blue-100">Install Bootloader</span> and press <span class="label">Enter</span>

![img](../../../assets/images//bios/48.png)

- Select <span class="text-blue-100">grub</span> (recommended) and press <span class="label">Enter</span> You can choose <span class="text-blue-100">syslinux</span> if you want.

![img](../../../assets/images//bios/49.png)

- Select the disk and press <span class="label">Enter</span> Wait till it's installed.

![img](../../../assets/images//bios/50.png)

- Go back to the main menu.

![img](../../../assets/images//bios/51.png)

- Select <span class="text-blue-100">Configure Base</span> and press <span class="label">Enter</span>

![img](../../../assets/images//bios/52.png)

- Select <span class="text-blue-100">Generate FSTAB</span> and press <span class="label">Enter</span>

![img](../../../assets/images//bios/53.png)

- Select <span class="text-blue-100">Device UUID</span> and press <span class="label">Enter</span>

![img](../../../assets/images//bios/54.png)

- Select <span class="text-blue-100">Set Hostname</span> and press <span class="label">Enter</span>

![img](../../../assets/images//bios/55.png)

- Enter the hostname (default is archcraft) and press <span class="label">Enter</span>

![img](../../../assets/images//bios/56.png)

- Select <span class="text-blue-100">Set System Locale</span> and press <span class="label">Enter</span>

![img](../../../assets/images//bios/57.png)

- I'm selecting <span class="text-blue-100">en_US.UTF-8</span>. Choose the one you want and press <span class="label">Enter</span>

![img](../../../assets/images//bios/58.png)

- Select <span class="text-blue-100">Set Timezone and Clock</span> and press <span class="label">Enter</span>

![img](../../../assets/images//bios/59.png)

- Select your continent. Mine's <span class="text-blue-100">Asia</span>

![img](../../../assets/images//bios/60.png)

- Select the city. Mine's <span class="text-blue-100">Kolkata</span>

![img](../../../assets/images//bios/61.png)

- Select <span class="text-blue-100">Yes</span> and press <span class="label">Enter</span>

![img](../../../assets/images//bios/62.png)

- Use <span class="text-blue-100">localtime</span> if you're dualbooting with Windows, otherwise UTC.

![img](../../../assets/images//bios/63.png)

- Select <span class="text-blue-100">Set Root Password</span> and press <span class="label">Enter</span>

![img](../../../assets/images//bios/64.png)

- Enter the password for the root account.

![img](../../../assets/images//bios/65.png)

- Select <span class="text-blue-100">Add New User(s)</span> and press <span class="label">Enter</span> You can create multiple user accounts here.

![img](../../../assets/images//bios/66.png)

- Type your username, must be lowercase. This will be your regular user account.

![img](../../../assets/images//bios/67.png)

- Enter the password for the new user.

![img](../../../assets/images//bios/68.png)

- And a regular user will be created.

![img](../../../assets/images//bios/69.png)

- Select <span class="text-blue-100">Security and systemd Tweaks</span> and press <span class="label">Enter</span>

![img](../../../assets/images//bios/70.png)

- Choose whichever tweaks you like. When you're done, hit Back.

![img](../../../assets/images//bios/71.png)

- Select <span class="text-blue-100">Review Configuration Files</span> and press <span class="label">Enter</span>

![img](../../../assets/images//bios/72.png)

- Here's a list of all config files you can review and modify.

![img](../../../assets/images//bios/73.png)

- When you're done reviewing & modifying config files, select <span class="text-blue-100">BACK</span> and press <span class="label">Enter</span>

![img](../../../assets/images//bios/76.png)

- Finally Select <span class="text-blue-100">Done</span> and press <span class="label">Enter</span>

![img](../../../assets/images//bios/77.png)

- Select <span class="text-blue-100">Yes</span> & exit the installer.

![img](../../../assets/images//bios/78.png)

That's it! Archcraft is installed on your system. Reboot the machine & enjoy your new OS.
{: .fs-6 .fw-300 }
