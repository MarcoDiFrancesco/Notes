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
