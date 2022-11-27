# ArchInstall
IMPORTANT: `lsblk` check for /dev/sda ELSE edit
`archinstall --config https://pastebin.com/raw/uhWrVskh`

Running this will install Y and *NetworkManager* packages
`su - marco`
`git clone https://github.com/marcodifrancesco/arch-installer /tmp/arch-installer`

Imwheel as user service
`systemctl --user enable --now imwheel.service`

#### Installation with script

Install git on live
`pacman -Sy git`

Make partition with BTRFS (-c for encryption by default)
`/pendrive/setup-base.sh`

Keep arch install date
`cp /pendrive/pacman.log /var/log/pacman.log`

Restart computer and exit from live
