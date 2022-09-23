# File manager
## Ranger
Ranger is installed from *community/ranger.*

Configuration files *commands.py* and *rc.conf* are overriding global config in */usr/share/doc/ranger/config/*. File *rifle.conf* is not ovverriding default config.

## xdg
### Config
Global .desktop files: */usr/share/applications*
Personalized .desktop files: *~/.local/share/applications/*

### Commands
`xdg-open file` open a file

`xdg-mime query filetype file.txt`  get the file type format

`xdg-mime query default video/x-matroska` get applications opening that file type

