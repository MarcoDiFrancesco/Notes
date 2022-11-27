# VM - WSL - SSH - Raspberry
## Raspberry setup
- Install image with Rufus
- Crete empty file */boot/ssh*
- Install vim, ranger, tmux
- Edit */etc/dhcpcd.conf*
    - `static ip_address=192.168.1.100/24`
    - `static routers=192.168.1.1`
- Edit */etc/ssh/sshd_config*
    - `PasswordAuthentication no`
- Docker, docker-compose, set permissions [link](https://dev.to/elalemanyo/how-to-install-docker-and-docker-compose-on-raspberry-pi-1mo)

Privoxy used as proxy


## VirtualBox

Guest additions are installed using *virtualbox-guest-iso* package.

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

### Python
Python is installed in */usr/bin/Python-x.x.x/* using:

```bash
# build-essential (make and gcc), zlib1g-dev (required by make install), and other from https://stackoverflow.com/a/44291036/7924557
sudo apt install build-essential zlib1g-dev libreadline-gplv2-dev libncursesw5-dev libssl-dev libsqlite3-dev tk-dev libgdbm-dev libc6-dev libbz2-dev
wget https://www.python.org/ftp/python/x.x.x/Python-x.x.x.tar.xz
tar xf Python-x.x.x.tar.xz
# Generate Makefile
./configure --enable-optimizations --with-ensurepip=install
sudo make install
```

### NanoPi / DietPi
NanoPi NEO, Dietpy

SSH Ports: 22 raspberry, 28 nano

Nano set using dropbear (a lightweight ssh), ssh keys set in *~/.ssh/authorized_keys* and config in */etc/default/dropbear*:

- DROPBEAR_PORT=28
- DROPBEAR_EXTRA_ARGS="-s" # To disable login without key
