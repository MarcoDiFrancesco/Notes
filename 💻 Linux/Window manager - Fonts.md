# Window manager - Fonts
## Windows manager

As windows manager *i3* is used

To open a floating window or full screen by default, the option for_window in config is used ([Reddit](https://www.reddit.com/r/i3wm/comments/4chax2/exec_with_fullscreen/)), to get the class name use xprop and click on the window ([Reddit](https://www.reddit.com/r/i3wm/comments/3h94t9/how_to_find_a_name_of_a_program_to_use_for/)).

Suspend and Auto lock in:

[[Screen - Sleep - Lock]]

- **Archive** Bspwm

## Bspwm

Removed because was not rendering Android Studio.

## Font

*extra/noto-fonts*

- set as default soft liking it in *~/.config/fontconfig/conf.d/*
- used in *i3* config

Used by URXVT and VSCode (set terminal.integrated.fontFamily):

- *aur/nerd-fonts-inconsolata*

Used by Polybar:

- *ttf-font-awesome* for personalized icons

Fonts to test:

```bash
ttf-bitstream-vera
ttf-dejavu
```
