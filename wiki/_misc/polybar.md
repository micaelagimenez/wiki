---
layout: default
title:  "polybar"
nav_order: 
---

# Polybar on Archcraft
Polybar is a highly customizable and very easy to use status bar that pairs well with window managers such as Openbox and Bdspwm. 

## Running the polybar
The polybar can be run with any of the following arguments:
`
Usage: polybar [OPTION]... BAR

  -h, --help               Display this help and exit
  -v, --version            Display build details and exit
  -l, --log=LEVEL          Set the logging verbosity (default: WARNING)
                           LEVEL is one of: error, warning, info, trace
  -q, --quiet              Be quiet (will override -l)
  -c, --config=FILE        Path to the configuration file
  -r, --reload             Reload when the configuration has been modified
  -d, --dump=PARAM         Print value of PARAM in bar section and exit
  -m, --list-monitors      Print list of available monitors and exit
  -w, --print-wmname       Print the generated WM_NAME and exit
  -s, --stdout             Output data to stdout instead of drawing it to the X window
  -p, --png=FILE           Save png snapshot to FILE after running for 3 seconds
`

## Configuration
The polybar can be edited in the folder `~/.config/polybar` where you can customize the different files according to your preferred theme.
Remember to run `-/.config/polybar/fix_modules.sh` to fix the polybar's icons upon first configuration.

### Modules
The polybar is designed with modules that you can customize to your advantage; you can also add or remove them. This file is called `modules.ini` and after making changes there you have to make sure to add the name of the modules to `config.ini` (depending on where you want the modules to appear, you must add them to 'modules-left', 'modules-right' or 'modules-center').
After making changes you should reload the polybar with `~/.config/polybar/{YOUR_THEME}/launch.sh` to be able to see them.
