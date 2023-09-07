# cheatsheet for linux

### create a super fast ram disk

    mkdir -p /mnt/ram
    mount -t tmpfs tmpfs /mnt/ram -o size=8192M

### show  ports on which the system listens on

    ss -tnl

### detect new hard disk attached without rebooting

    for host in /sys/class/scsi_host/*; do echo "- - -" | sudo tee $host/scan; ls /dev/sd* ; done

### nslookup

    nslookup -port=8053 ns1.lab-net.lan localhost
