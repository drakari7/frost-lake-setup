## Welcome

This repo contains the dotfiles for my first rice setup on Arch-Linux. <br />

## Table of contents

- fonts
- i3 configuration file
- kitty configuration file
- polybar configuration files

## Dependancies
- The icon fonts are required by polybar to work, otherwise you may get **Dropping character** errors from running polybar.

- [compton-tryone-git](https://github.com/tryone144/compton)
Required for the kawase blur effect. Arch users can install it from AUR [tryone-fork of compton](https://aur.archlinux.org/packages/compton-tryone-git/)

- [polybar-spotify-module](https://github.com/mihirlad55/polybar-spotify-module)
Required by polybar to use the spotify module. Arch users can install it from AUR [link](https://aur.archlinux.org/packages/polybar-spotify-module/)



## How to setup

Clone the repo first. After cloning, place all these files in your ***~/.config*** folder with the following commands.

```bash
#clone the repo

#enter the directory
cd frost-lake-setup

#put fonts in the place you store fonts (you might want to put them in /usr/share/fonts/TTF instead)
cp fonts/* ~/.fonts/

#reload font-cache
fc-cache -v

#copy everything except the fonts to your .config folder (you might want to backup your existing config files in case things go awry)
rm -rf fonts/
cp -r * ~/.config/

```

## Kitty config files
Copy the config files. [Additional documentation can be found here](https://sw.kovidgoyal.net/kitty/conf.html). <br /> 
You might want to change the color theme as per your wish. Simply change the values of the colors in theme.conf, or find a preset on the internet. <br />

## i3 config file
Contains the regular keybindings for i3wm. You will have to edit the file in order to make it work on your system. Alternatively, I recommend just copy pasting the autostart section to your own config file as some of those commands are needed to startup compton polybar etc.

## Polybar-Setup

The original polybar setup has been borrowed from this brilliant [polybar-theme-repo](https://github.com/adi1090x/polybar-themes). In case of errors, follow the instructions in the link step by step. There are other polybar-themes in the repo as well. I'm using theme-5. <br />

I have configured some of the modules, tweaked the layout, and most notably installed the spotify module seperately. 

***Do not forget to install the polybar-spotify-module mentioned above if you want to use it***

Most common sources of errors arise from missing fonts. <br />

**errors I came across in my installation**: 

- if the battery module isn't working, try setting battery=BAT1 instead of BAT0.
- A successful method of debugging that worked for me was, run the individual bar commands (top and bottom,found in launch.sh) in a terminal, and note the output. Polybar gives a very detailed output, and you will be able to figure out the issues by googling the error messages.