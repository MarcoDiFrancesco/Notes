# Keyring
*extra/gnome-keyring* is the keyring currently used used. It allows things like chromium and git to store password safely.

It is sourced on *startx* in *~.xinitrc* using:

```bash
eval $(/usr/bin/gnome-keyring-daemon --start --components=pkcs11,secrets,ssh)
dbus-update-activation-environment --systemd DISPLAY
```

The passowrd is required the first time a program requires it.