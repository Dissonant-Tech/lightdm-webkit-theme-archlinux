# lightdm-webkit-theme-archlinux


## Overview

This is a slightly modified version of the: 

Official LightDM Webkit Greeter Theme of Antergos Linux

This version only changes the Antergos icons into official Arch icons from the 
[archlinux-artwork][4] package for those with a base Arch install that would like
the proper logos while using the (very beautiful) Antergos greeter theme.

Original can be [found here][1]. All credit goes to the great people who 
created, run, and maintain [Antergos][2].

## Screenshots
<img src="img/screenshot1.jpg" alt="screenshot1" />

## Prerequisites

* lightdm
* lightdm-webkit2-greeter
* antergos-wallpapers (used for the background switcher)

Enable `ligthdm-webkit2-greeter` by editing `/etc/lightdm/lightdm.conf` and setting `greeter-session` property to `lightdm-webkit2-greeter` :

```
[SeatDefaults]
#greeter-session=lightdm-gtk-greeter
greeter-session=lightdm-webkit2-greeter
user-session=your-session (gnome,cinnamon,xfce...)

```

# Installation

Can be installed through the AUR.

This package does not conflict with [lightdm-webkit-theme-antergos][5]. To switch
between the two just change the `webkit-theme=`  in `/etc/lightdm/lightdm-webkit2-greeeter.conf`
to either `archlinux` or `antergos`.

# Uninstallation

To uninstall, simply restore the `greeter-session` property of the `/etc/lightdm/lightdm.conf` file and restart your computer (or at least lightdm).

You may also want to :
* Remove the folder `archlinux` which was created in `/usr/share/lightdm-webkit/themes/`
* Restore the `webkit-theme` property of the `/etc/lightdm/lightdm-webkit-greeter.conf` file

# User icons management

To change users icons, there are two options :

* Create a `.face` file in the user's home folder in which you put a `jpg` or `png` resource

Or 

* Create a resource named with the user's login in `/var/lib/AccountsService/icons/`
* Edit `/var/lib/AccountsService/users/<userLogin>` and add a property `Icon` targeting the icon resource you just created

Read more at the [ArchWiki LightDM][3] page.

This theme works well with 96x96 images.


[1]: https://github.com/Antergos/lightdm-webkit-theme-antergos
[2]: http://antergos.com/
[3]: https://wiki.archlinux.org/index.php/LightDM#Changing_your_avatar
[4]: https://aur.archlinux.org/packages/archlinux-artwork/
[5]: https://aur.archlinux.org/packages/lightdm-webkit-theme-antergos/
