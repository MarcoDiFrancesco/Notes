`fsck`, File System Consistency Check, checks addresses file system-level issues. Does not provide information about the physical health of the storage device itself.

```
sudo fsck /dev/sdX1
```


SMART, Self-Monitoring Analysis and Reporting Technology, is a technology 
Smartmontools, checks health of  that support
```
sudo smartctl -a /dev/sdX
```