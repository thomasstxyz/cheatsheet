# cheatsheet for bash

### remove all commented lines in a file

    cat file | grep -vE '^(\s*)#'
    awk -F '#' '($0 !~ /^[[:space:]]*#.*$/ && NF) {print $1}' $1

### leave a busy terminal but leave process running in background.

    Ctrl+Z
    bg
    disown
    exiti

### terminate a frozen ssh session

    press "Enter", "~" and "." one after another in that order.

if you are connected from A to B, and from B to C:

    press ~~ tilde twice

### listen on oncoming ip traffic with tcpdump

    tcpdump -l -n -i eth0 dst port 80 and inbound

### lsof

find out who is looking what files and commands

    lsof -i -u username

list user specific open files

    lsof -u username

find processes running on specific port

    lsof -i TCP:22

list all network connections

    lsof -i

list only IPv4 & IPv6 open network files

    lsof -i 4
    lsof -i 6

list open files of port ranges

    lsof -i TCP:1-1024

exclude user with ^ char

    lsof -i -u^root

search by PID

    lsof -p 1

kill all activity of particular user

    kill -9 $(lsof -t -u username)

### check if website exists

    wget -S --spider https://www.thomasst.xyz

### find files knowing and searching only text inside of the files

find + grep

    find ./ -type f -iname "*" -exec grep -i -n "textinsidethefile" {} +

grep -r

    grep -rniI "search_term" .

### rename file extensions of all files in a directory / bash parameter expansion

The code can be used to rename all JPEG files with a .JPG or a .jpeg extension
to have a normal .jpg extension. The expression ${file%.*} cuts off everything
from the end starting with the last period (.).
Then, in the same quotes, a new extension is appended to the expansion result.

    for file in *.JPG *.jpeg
    do mv -- "$file" "${file%.*}.jpg"
    done

### find files by file extension and sort by size

    find . -type f -printf '%s %f\n' | awk '{ size = $1; ext = ""; if(sub(/.*\./, "") != 0) { ext = $0 }; total[ext] += size; ++ctr[ext]  } END { PROCINFO["sorted_in"] = "@ind_str_asc"; for(ext in total) { print ext " " ctr[ext] " " total[ext] } }' | awk -F ' ' '{print $3,$1,$2}' OFS=' ' | sort -g

### Here Documents

https://www.gnu.org/savannah-checkouts/gnu/bash/manual/bash.html#Here-Documents
