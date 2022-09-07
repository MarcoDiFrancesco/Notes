# Screen - Sleep - Lock
## Screen saver / Auto sleep

Script: *lock.* Config: *i3.*

Screen saver screen after 10 minutes (default behaviour) disabled in */etc/X11/xorg.conf.d/10-monitor.conf*. It's possible to see option using `xset q` in screen saver, timeout.

*aur/xidlehook* used to detect usage instead of *xset*.

- **archive** *community/xautolock*

    Replaced because it's not possible to not lock scren on video, the solution I don't like would be to put arrow on the corners ([reddit](https://www.reddit.com/r/i3wm/comments/ak8fjy/how_do_you_guys_suspend_xautolocki3lock_when/))

## Disable wake on muse/trackpad move from sleep

??? WORKS also if serverice isn't there ?????

Added in */etc/systemd/system/disable-keyboard-wakeup.service* and enabled it ([reddit](https://www.reddit.com/r/archlinux/comments/3zxg65/how_to_permanently_change_procacpiwakeup_or/))

```bash
[Unit]                                                                           
Description=Disable external keyboard and mouse wakup

[Service]
ExecStart=/bin/bash -c "echo XHC >> /proc/acpi/wakeup"

[Install]
WantedBy=multi-user.target
```