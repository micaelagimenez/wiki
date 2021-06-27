---
layout: post
title:  "Frequently Asked Questions"
nav_order: 1
---

# Frequently Asked Questions

These are the most asked questions about Archcraft.

<!---->

<details close markdown="block">
  <summary>
	How to add music to bar?
  </summary>
{: .text-green-300}

To add your favorite music to polybar, follow the steps below :

- Open a terminal and **Kill the mpd daemon**

```bash
$ pkill mpd
```

- Now delete the existing **mpd database file**

```bash
$ cd ~/.mpd
$ rm mpd.db
```

- Now, Start the **mpd daemon** again and open `ncmpcpp`

```bash
$ mpd &
$ ncmpcpp
```

- In ncmpcpp, press **2** and you'll get a list of all songs present in your **~/Music** directory.
- Select your songs and press <span class="label">SPACE</span> to add the songs in your current playlist.
  
</details>

<!---->

<details close markdown="block">
  <summary>
	How to change theme and icons in Bspwm?
  </summary>
{: .text-green-300}

In Archcraft, Bspwm use `xsettingsd`, a daemon that implements the XSETTINGS specification.
To change gtk theme, icons and cursor theme, you need to edit the **~/.xsettingsd** file 

- Edit **~/.xsettingsd** file with your favorite text editor

```bash
$ vim ~/.xsettingsd
```
  
- Change the values of following lines according to the stuff you want to apply

```bash
Net/ThemeName "Arc-Dark"
Net/IconThemeName "Arc-Circle"
Gtk/CursorThemeName "Arc-Cursor-Dark"
```

- Restart the `xsettingsd` daemon. Have a look at [this](https://github.com/derat/xsettingsd/wiki/Settings) for all options.

</details>

<!---->
