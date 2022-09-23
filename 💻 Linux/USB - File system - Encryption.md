# USB - File system - Encryption
Link: [[VM - WSL - SSH - Raspberry]]

## Pendive - USB
Create martitions: `sudo cfdisk /dev/sdC`

- New > primary (dos)
- Type > *W95 FAT32 (LBA)*
- Bootable

Write tables `sudo mkfs.fat /dev/sdC1` (mkfs.vfat is a symlink to fat)

## Tar
To compress a file with tar: `tar -cpvzp enctrypted.tar.gz folder-to-encrypt`

Tar options: 
- c, --create create a new archive
- p, --preserve-permissions, --same-permissions
- v, --verbose verbosely list files processed
- z, --gzip, --gunzip, --ungzip filter the archive through gzip
- f, --file=ARCHIVE use archive file or device ARCHIVE

7zip on Windows does not support files enctypted with OpenSSL

## File enctyption
GPG vs OpenSSL, at the end GPG is used: [link](https://stackoverflow.com/questions/28247821/openssl-vs-gpg-for-encrypting-off-site-backups)

### Setup
`gpg --full-gen-key` to generate a new key

`gpg --armor --export marcodifran@gmail.com > key.pub` to export key in ascii

Public key is placed in *~/.config/gnupg/key.pub*

`gpg --armor --export-secret-key marcodifran@gmail.com > private.pgp` to export 

`gpg --import key.pub` to import the key, also if it is in ascii format, this will import also the Name, Comment and Email of the person that created this key

### Usage

`gpg --recipient marcodifran@gmail.com --encrypt file` creates a binary called *file.gpg* in the same folder*.* --armor in this case would encode the file in ascii, useful in case it's not possibile to transfer a binary into the network. --output file.gpg to specify output file

`gpg --decrypt file.gpg > file` decrypt file.gpg into file, it does not require the key specified in the command becuase the file already contains who owns the file

## Archive
### Btrfs installation
To mount btrfs subvolume from live use the preinstalled crypsetup command:

```bash
cryptsetup open /dev/nvme0n1p2 mydisk # To decrypt disk
mount -t btrfs -o subvol=@ /dev/mapper/mydisk /mnt/mymnt
mount -t btrfs -o subvol=@opt /dev/mapper/mydisk /mnt/mymnt/opt
mount -t btrfs -o subvol=@var_log /dev/mapper/mydisk /mnt/mymnt/var/log
```

After the installation in case the system is broken and another snapshot has been made edit */etc/fstab*, in the *subvol=@mysuvolue* set a snapshot using either the path (*@home* or *var/lib/portables*) or the id (like *subvol=345*).

Another possibility to check the files inside a snapshot is just mounting it in a directory.

## Btrfs usage
For btrfs utilities *core/btrfs-progs* is installed in the system (not in live) and usable with the *btrfs* command.

`sudo btrfs subvolume snapshot / /snapshot/base` to **create snapshot**

`sudo btrfs subvolume show /home` to get **subvolume details** like related snapshots.

`sudo btrfs subvolume list /snapshot -to` to **list subvolumes** in snapshot directory. Specifying */home* to the command does not work becase the partend id (same thing as top level) of the snapshot called *@snapshot/2020-12-05_11:38:01_home_cron* is pointing to */snapshot*. This is a design choice made by Federico and the other Guy.

`sudo btrfs filesystem du /var/log -s` to get the **subvolume used disk** and its releated snapshots:

```bash
Total       80.61GiB  # Total space
Exclusive   166.29MiB # Space used only by this snapshot
Set shared  54.77GiB  # Shared space between snapshots
Filename    /home
```

`sudo btrfs filesystem usage /` to get the **disk usage**, specifying */* or */var/log* is the same becuase they are installed in the same disk (nvme one).

Snapshots are made in using a root service in crontab: [[Crontab - Events - Udev]]
