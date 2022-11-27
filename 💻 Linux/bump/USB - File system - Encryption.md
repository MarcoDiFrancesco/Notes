# USB - File system - Encryption
Link:
- [[VM - WSL]]
- [[]]
## Pendive - USB
Create martitions: `sudo cfdisk /dev/sdC`

- New > primary (dos)
- Type > *W95 FAT32 (LBA)*
- Bootable

Write tables `sudo mkfs.fat /dev/sdC1` (mkfs.vfat is a symlink to fat)
