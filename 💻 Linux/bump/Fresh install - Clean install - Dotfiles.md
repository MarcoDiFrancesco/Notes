# Fresh install - Clean install - Dotfiles
## Dotfiles
Files managed in home directory with bare repostiory.
Root files not managed by any program (e.g. Chezmoi) becase they do not support by default root files ([link](https://github.com/twpayne/chezmoi/discussions/1510#discussioncomment-1453461)), and most of the times I don't want to have all root files copied in the new system.

## ArchInstall
IMPORTANT: `lsblk` check for /dev/sda ELSE edit
`archinstall --config https://pastebin.com/raw/uhWrVskh`

Running this will install Y and *NetworkManager* packages
`su - marco`
`git clone https://github.com/marcodifrancesco/arch-installer /tmp/arch-installer`

Imwheel as user service
`systemctl --user enable --now imwheel.service`

### Backup before clean
- about:config changed settings

### Root files to be copied on post install
List of system files (non-dotfiles) that need to be copied after install. These files should all be backed up by a full system backup in the hdd.

- ~/.ssh
- ~/.cache/zsh/history

- /etc/environment
- /etc/udev/rules.d/ (for keyboard setup and logkeys start)
	- /var/log/logkeys/
- /etc/X11/xorg.conf.d/

Pacman:
- /etc/pacman.conf
- /etc/pacman.d/hooks
- /var/log/pacman.log

Network Manager:
- /etc/NetworkManager/NetworkManager.conf
- /etc/NetworkManager/system-connections/

Firefox:
- search engine (search.json.mozlz4)
- ~/.local/share/activitywatch

Anki (for extensions):
- ~/.local/share/Anki2

#### Archive Manual installation

Format disk: `cfdisk /dev/nvme0n1`

- Encryption

Initialize a luks partition, flag -y for asking passphrase twice and -v for verbose

`cryptsetup -y -v --type luks2 luksFormat /dev/nvme0n1p2`

Decrypt partition and mount it

`cryptsetup open /dev/nvme0n1p2 cryptroot`

Create filesystem on partition

`mkfs.vfat /dev/nvme0n1p1`

`mkfs.ext4 /dev/nvme0n1p2` or `mkfs.ext4 /dev/mapper/cryptool`

Mount root

`mount /dev/nvme0n1p2 /mnt` or `mount /dev/mapper/cryptool /mnt`

Mount boot partition

`mount /dev/nvme0n1p1 /mnt/boot` or `mount /dev/nvme0n1p1 /mnt/boot`

Install programs:

`pacstrap /mnt base linux linux-firmware man-db man-pages git grub efibootmgr networkmanager vim`

Generate fstab

`genfstab -U /mnt >> /mnt/etc/fstab`

- Encryption

Setup [crypttab](https://wiki.archlinux.org/index.php/Dm-crypt/System_configuration#crypttab) (the device table similar to fstab for encrypted devices)

`cp /mnt/etc/crypttab /mnt/etc/crypttab.initramfs`

Write the root partition ID in *crypttab.initramfs*

`lsblk -dno UUID /dev/nvme0n1p2 >> /mnt/etc/crypttab.initramfs`

And adjust the content to make something like:

```jsx
cryptroot       UUID=0000000000-0000-0000-0000-0000-0000000000   luks,discard
```

Edit hooks line in */mnt/etc/mkinitcpio.conf* (mkinitcpio was run on installation of the kernel package with pacstrap, so it's already generated)

```jsx
HOOKS=(base udev autodetect **keyboard keymap** consolefont modconf block **encrypt** filesystems fsck)
```

Chroot in system

`arch-chroot /mnt`

Edit */etc/locale.gen* and uncomment *en_US.UTF-8 UTF-8*

Generate locale

`locale-gen`

Set locale (not the same as above)

`localectl set-locale LANG=en_US.UTF-8`

- Encryption

NOT DONE FOR NOW Set boot loader parameters, in */etc/default/grub* add command in 5th line

`GRUB_CMDLINE_LINUX="cryptdevice=/dev/nvme0n1p2:cryptroot"`

Generate init frames, *-P* to regenerate all presets, *-p linux* to regenerate only linux preset, already done when pacstrapping *linux-firmware* (or maybe *linux*)

`mkinitcpio -P`

Regenerate grub, *--target=x86_64-efi* is set by default, *--bootloader-id=GRUB* I don't know what it does

`grub-install --efi-directory=/boot`

grub-install --target=x86_64-efi --efi-directory=/boot --bootloader-id=GRUB

`grub-mkconfig --output /boot/grub/grub.cfg`

Set password for root

`passwd`

Keep arch install date

`cp /pendrive/pacman.log /var/log/pacman.log`

Restart computer and exit from live

- **Archive** Installation with script

#### Archive Installation with script

Install git on live

`pacman -Sy git`

Make partition with BTRFS (-c for encryption by default)

`/pendrive/setup-base.sh`

Keep arch install date

`cp /pendrive/pacman.log /var/log/pacman.log`

Restart computer and exit from live


#### Archive Partitions
![](https://i.imgur.com/yXl9W6T.png)
