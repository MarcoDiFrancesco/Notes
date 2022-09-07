# GoPro
*simple-mtpfs* installed to mount it

```sh
# List devices
sudo simple-mtpfs --list-devices
mkdir ~/Downloads/gopro
# Mount device to directory
simple-mtpfs --device 1 ~/Downloads/gopro
ls ~/Downloads/gopro/DCIM
cp -rv ~/Downloads/gopro/DCIM ~/Downloads
```
