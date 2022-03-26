# cheatsheet for linux

### create a super fast ram disk

    mkdir -p /mnt/ram
    mount -t tmpfs tmpfs /mnt/ram -o size=8192M

### show  ports on which the system listens on

    ss -tnl
