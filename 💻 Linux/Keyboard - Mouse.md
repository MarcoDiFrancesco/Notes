# Keyboard - Mouse
## Keyboard
Script: *script/keyboard*
*xdotool* used to toggle caps

### Basic
`setxkbmap -layout us -variant altgr-intl` to set "English (intl., with AltGr dead keys)"

**International** layout (*intl*) changes the ~ ^ ' " into **dead keys**, keys that do not work until another key is typed.
International **AltGr** (*altgr-intl*) is a variant switch the role of the AltGr (alternate graph) key, requiring to click it in combination with ~ ^ ' " to enable a dead key

![](https://i.imgur.com/AJrhUuL.png)

### Personalized
Script: *~/.config/xkb/map*
Set on keyboard script, startuped in *i3*.

Keyboard map in *~/.config/xkb/map* generated with
`setxkbmap -layout us -variant altgr-intl -print > map-tmp`

![](https://i.imgur.com/nljZu08.png)

**Keycodes**
- numbers (79, 118) are visible with `xev`
- values (RGHT, AD08) in file */usr/share/X11/xkb/keycodes/evdev*

**Symbols** (0, a, Right) in `xev`

Default folders can be found in */usr/share/X11/xkb* and other folders can be sourced using -I (in the following command)
`xkbcomp -I$HOME/.config/xkb ~/.config/xkb/map $DISPLAY`

## Mouse
Tap-to-click was enabled in */etc/X11/xorg.conf.d*
List devices options: `sudo libinput list-devices`
Translate options (https://man.archlinux.org/man/libinput.4)

## Key logger
*logkeys-start* script
Started from `systemctl logkeys`

#### Archive mouse
- **Archive** Emoji picker
    Package `community/rofimoji` set in mod+shift+d shortcut

#### Archive xmodmap
xmodmap: changed directly in *setxkbmap*
`~/.config/xkb/symbols/caps-to-mod`

#### Archive key bindings
*xbindkeys* changed in favor of *sxhkd*, it allows to specify multiple keybinding to the same command.

*sxhkd* changed in favor of *i3* config