# Internet - NetworkManager

## Network manager
Avoid hostname change
*/etc/NetworkManager/NetworkManager.conf*
```bash
[main]
hostname-mode=none
```

## Network tools
*core/iproute2* (preinstalled): replaces arp, ifconfig, route.
*ss* package replaces netstat

`ip addr` to get ip
`ss -at` to get all tcp connections
`lsof` is used to get open files, `-p :5432` to get port
