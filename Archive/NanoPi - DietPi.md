NanoPi NEO, Dietpy

SSH Ports: 22 raspberry, 28 nano

Nano set using dropbear (a lightweight ssh), ssh keys set in *~/.ssh/authorized_keys* and config in */etc/default/dropbear*:

- DROPBEAR_PORT=28
- DROPBEAR_EXTRA_ARGS="-s" # To disable login without key
