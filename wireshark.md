# cheatsheet for wireshark

all icmp echo requests

    icmp.type==8 and icmp.code==0

all traffic communicating on TCP port 3389

    tcp.port == 3389

all packets where destination port is 3389

    tcp.dstport == 3389  # tcp.srcport for source port

all traffic between 2 ip addresses

    ip.addr == 192.168.1.117 and ip.addr == 192.168.1.151  # && can also be used instead of  and

all hosts that make HTTP GET requests to cisco.com

    http.request.method == GET and http.host contains "cisco.com"

packets where source ip is x

    ip.src == 192.168.1.117
