---
layout: post
title:  "Build Archcraft ISO"
nav_order: 0
---

# Build Archcraft ISO

If you are already using Arch Linux or Archcraft and want to build the ISO yourself, maybe with your configs and additional programs, follow the steps below to successfully build the Archcraft ISO.

### Checklist

- [ ] archiso version : 55-1
- [ ] At least 10GB of free space.
- [ ] Arch Linux 64-bit only.
- [ ] Clear pacman cache; sudo pacman -Scc.

### Build

- Open terminal and clone the Archcraft repository.

```bash
$ git clone --depth=1 https://github.com/archcraft-os/archcraft.git
```

- After cloning, change to the archcraft directory and run `setup.sh`

```bash
$ cd archcraft
$ chmod +x setup.sh
$ ./setup.sh						
```

- Now, Change to the iso directory and run `mkarchcraftiso` as root.

```bash
$ cd iso
$ sudo su
# ./mkarchcraftiso -v .						
```

- If everything goes well, you'll have the ISO in the iso/out directory.


If you want to rebuild the ISO, make sure to first remove the **work** and **out** directories inside the **iso** directory. Then run `./mkarchcraftiso -v .` as root. You don't need to run `setup.sh` again, it's only a one time process. 
