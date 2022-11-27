# SSL Pinning
## Android studio
Packages *aur/android-studio* and *aur/android-sdk*, *aur/android-sdk-platform-tools* (for adb).

Run as sudo or create user:
```bash
groupadd android-sdk
gpasswd -a marco android-sdk
sudo setfacl -R -m g:android-sdk:rwx /opt/android-sdk
sudo setfacl -d -m g:android-sdk:rwX /opt/android-sdk
# Reboot or 'newgrp android-sdk'
```

SSL pinning:
```bash
adb push frida-server /data/local/tmp/
# Adb
adb root
chmod 755 /data/local/tmp/frida-server
/data/local/tmp/frida-server

# In terminal
source ~/Downloads/.venv/bin/activate
frida --codeshare akabe1/frida-multiple-unpinning -U -f it.unitn.unitrentoapp --no-pause
```

Android emulators not used: Arch images ([link](https://aur.archlinux.org/packages/?K=android-+system+image)) not save ([link](https://www.reddit.com/r/privacytoolsIO/comments/hdvc6i/foss_android_emulator_for_arch_linux/)).

*aur/android-x86-64-system-image* anyway gave Java stack trace on startup.



