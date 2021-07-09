---
layout: default
title:  "Openbox"
nav_order: 0
---

# Openbox Window Manager

Openbox is the primary window manager of Archcraft.

## Configuration
There are three main files thata allow openbox to be configured: `rc.xml`, `menu.xml` and `autostart`.

### rc.xml
`~/.config/openbox/rc.xml`
This file controls the behavior and settings of the session:
- Keyboard shortcuts.
- Theming.
- Desktop and Virtual desktop settings.
- Application Window settings.

### menu.xml
`~/.config/openbox/menu.xml`
This file controls the type and behaviour of the desktop menu.

### Autostart
`~/.config/openbox/autostart`
This file allows you to add your startup programs (Add an '&' symbol at the end of the command).

## Key Bindings
The <span class="label label-green">SUPER</span> or <span class="label label-green">WINDOWS</span> key is the default **Modkey**. 

### Window Manager
{: .no_toc }

|Key|Action|
|:--|:--|
|<span class="btn btn-purple">W + [1..5]</span>|Switch to workspace 1..5|
|<span class="btn btn-purple">S + W + [1..5]</span>|Send to workspace 1..5|
|<span class="btn btn-purple">A + Tab </span>|Next Window|
|<span class="btn btn-purple">W + Tab </span>|Next Window|
|<span class="btn btn-purple">W + L</span>|Unmaximize Full|
|<span class="btn btn-purple">W + R</span>|Unmaximize Full|
|<span class="btn btn-purple">W + Up</span>|Maximize Full|
|<span class="btn btn-purple">W + Down</span>|Unmaximize Full|
|<span class="btn btn-purple">W + K/H/J/L</span>|Unmaximize|
|<span class="btn btn-purple">A + Z/X/C</span>|Unmaximize|
|<span class="btn btn-purple">W + A + Up/Down/Left/Right</span>|Move Relative|
|<span class="btn btn-purple">C + A + Up/Down/Left/Right</span>|Resize Relative|
|<span class="btn btn-purple">W + S + Left</span>|Send To Desktop Left|
|<span class="btn btn-purple">W + S + Right</span>|Send To Desktop Right|

### Applications
{: .no_toc }

|Key|Action|
|:--|:--|
|<span class="btn btn-green">W + T</span>|Open Terminal Emulator Fullscreen (alacritty)|
|<span class="btn btn-green">W + F</span>|Open File Manager (thunar)|
|<span class="btn btn-green">W + E</span>|Open Text Editor (geany)|
|<span class="btn btn-green">W + W</span>|Open Web Browser (Midori)|

## Styles
You'll find a folder with styles at `~/.config/openbox`. Edit them or add your own to customize it.
