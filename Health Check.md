### Hardware health

SMART, Self-Monitoring Analysis and Reporting Technology, is a technology managed by the chip of SSDs and HDDs. It continuously monitors parameters that include: number of read/write errors, temperature, power-on hours.

`smartctl` uses SMART to check health of the device.
```
sudo smartctl -a /dev/sdX
```

### OS health

`fsck`, File System Consistency Check, checks addresses file system-level issues. Does not provide information about the physical health of the storage device itself.

```
sudo fsck /dev/sdX1
```

