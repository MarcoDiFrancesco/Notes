# VM - WSL

## VirtualBox

Guest additions are installed using *virtualbox-guest-iso* package

*virtualbox-host-modules-arch* is installed for linux kernel ([info](https://wiki.archlinux.org/index.php/VirtualBox))

Enable internet: [https://askubuntu.com/a/424368/877408](https://askubuntu.com/a/424368/877408)

![](https://i.imgur.com/VhkEo5x.png)

## WSL

In this page some program specific for WSL are listed:

- Node: *nvm* has been installed from [microsoft website](https://docs.microsoft.com/en-us/windows/nodejs/setup-on-wsl2)
- `nvm ls` to list node and npm versions
- CUDA gets disabled after sleep [link](https://askubuntu.com/questions/607118)

## Archive
### Netbeans
Installed on Ubuntu 18.04 (on 20.04 library versions are not available)

Installed version 8.2 old or rc (both work)

```bash
sudo apt purge openjfx # Remove if installed
sudo apt install vim curl openjdk-8-jdk openjfx=8u161-b12-1ubuntu2 libopenjfx-jni=8u161-b12-1ubuntu2 libopenjfx-java=8u161-b12-1ubuntu2
sudo apt-mark hold openjfx libopenjfx-jni libopenjfx-java
curl -O https://download.netbeans.org/netbeans/8.2/final/bundles/netbeans-8.2-linux.sh
sudo chmod +x ./netbeans-8.2-linux.sh
./netbeans-8.2-linux.sh

# Replace the line below 
# netbeans_jdkhome="/usr/lib/jvm/java-1.8.0-openjdk-amd64"
vim ~/netbeans-8.2/etc/netbeans.conf
```

### NanoPi / DietPi
NanoPi NEO, Dietpy

SSH Ports: 22 raspberry, 28 nano

Nano set using dropbear (a lightweight ssh), ssh keys set in *~/.ssh/authorized_keys* and config in */etc/default/dropbear*:

- DROPBEAR_PORT=28
- DROPBEAR_EXTRA_ARGS="-s" # To disable login without key
