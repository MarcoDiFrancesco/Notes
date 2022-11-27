# BTRFS
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

### Btrfs usage
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
