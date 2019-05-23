# Configuration files for my Arch Linux install

![alt text](screenshot1.png)

Window Manager: [i3-gaps](https://github.com/Airblader/i3) + [justbuchanan's i3 scripts](https://github.com/justbuchanan/i3scripts)
Application Launcher: [Rofi](https://github.com/davatorium/rofi)
Status Bar: [Polybar](https://github.com/polybar/polybar)

### Contents

- [Login Manager](#login-manager)
- [Desktop](#desktop)
- [Status Bar](#status-bar)
- [Launcher](#launcher)
- [Theming](#theming)
- [Notifications](#notifications)

___

## Login Manager
No login manager is used.
The [Autostart X at login](https://wiki.archlinux.org/index.php/Xinit#Autostart_X_at_login) method is used which negates the need for a login manager. This requires xinit.

`~/.zprofile`

    if [[ ! $DISPLAY && $XDG_VTNR -eq 1 ]]; then
      exec startx
    fi

## Desktop
Window Manager: [i3-gaps](https://github.com/Airblader/i3) used for tilling capabilities
![alt text](Gif1.gif)

## Status Bar
[Polybar](https://github.com/polybar/polybar)

Custom modules added:
[battery-combined-udev](https://github.com/polybar/polybar-scripts/blob/master/polybar-scripts/battery-combined-udev): uses udev rules to check the battery status. Supports multiple batteries.
[player-mpris-tail](https://github.com/polybar/polybar-scripts/blob/master/polybar-scripts/player-mpris-tail): Uses the tail functionality of Polybar in order to update in real-time.
[pulseaudio-tail](https://github.com/polybar/polybar-scripts/blob/master/polybar-scripts/pulseaudio-tail): Also uses tail to update volume in real time even when switching it from different places

The configuration files are split in folders for easy editing. 

## Launcher
Application Launcher: [Rofi](https://github.com/davatorium/rofi)
Rofi is also used for the shutdown menu (set to mod + x)

## Theming
Theming is done almost system-wide using [wpgtk](https://github.com/deviantfero/wpgtk).
Wpgtk sets a wallpaper and then generats a color scheme which it applies to various config files.
This makes the color scheme automatically adjust to match the wallpaper.
## Notifications
[Dunst](https://github.com/dunst-project/dunst) handles notifcations. At the moment it is not fully implemented and integrated with any applications other then the usb-daemon.
