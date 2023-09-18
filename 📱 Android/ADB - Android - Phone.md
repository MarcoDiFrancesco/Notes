## ADB
Connect: `adb shell`
List apps: `pm list packages`, `-e` and `-d` for enabled/disabled apps
Disable: `pm disable-user --user 0 com.example`
Enable: `pm enable com.example`
App version: `dumpsys package com.example | grep versionName`

Disabled packages:
```shell
# Sim Toolkit - e.g. WindTre Toolkit
com.android.stk

# Google assistant shortcut from bottom
com.google.android.googlequicksearchbox
# Google assistant also, since was not working without the app above
com.google.android.apps.googleassistant

# Oppo Android 11
com.heytap.music
com.coloros.backuprestore
com.coloros.weather2
com.coloros.compass2
com.coloros.calculator
com.coloros.alarmclock
com.coloros.filemanager
com.coloros.soundrecorder
# Oppo Android 12
com.coloros.phonemanager
com.oplus.games
```

## Frida
Frida server on:
[[SSL Pinning]]