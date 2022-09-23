# Software - Programs - Viewer - Editor
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

## CURL vs WGET
curl:
- Support upload and download from the server
- Uses libcurl, a widely adopted library to download files from the servers

wget:
- Allows to download recursively files from a server for example a directory given in FTP

## Code editor
IntelliJ Idea: packages *intellij-idea-community-edition*, *javafx, openjdk*

When creating a new JavaFX project:
Run -> edit configurations -> Modify options -> Add VM options -> *Paste in VM options*

```jsx
--module-path /usr/lib/jvm/java-11-openjfx/lib --add-modules javafx.controls,javafx.fxml
```

Works also without it: ctrl + shift + alt + s -> + (at the bottom) -> Library -> JavaFX

## Firefox
In settings `about:config` option `pdfjs.defaultZoomValue` set `page-fit` ([link](https://github.com/mozilla/pdf.js/pull/3850#issue-9432860))

## Image
View pictures:
- Almost all: Eye Of Gnome (*extra/eog*)
- SVG: display command (from image magick)

Edit pictures via cli *extra/imagemagick*

Walpaper *extra/feh*

## PDF
Split and merge PDF *community/pdfarranger*

Sign PDF *community/xournalpp*

## Spotify
*spotify* is used as a PWA with ads blocked by uBlock

Backup is made using [https://www.tunemymusic.com/](https://www.tunemymusic.com/)

## Video
Video editor *community/shotcut*

