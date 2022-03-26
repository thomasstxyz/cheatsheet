# cheatsheet for powershell

### NTFS alternate data streams (hide a file inside a regular file)

append text file

    echo my hidden text > hello.txt:mystream

view content

    Get-Content -path .\hello.txt -stream hidden

append executable

    Set-Content -path .\hello.txt -value $(Get-Content $(Get-Command calc.exe).Path -readcount 0 -encoding byte) -encoding byte -stream exestream

launch the hidden executable file

    wmic process call create $(Resolve-Path .\hello.txt:exestream)

finding alternate data streams

    Get-ChildItem -recurse | ForEach { Get-Item $_.FullName -stream * } | Where stream -ne ':$DATA'

### special characters in Windows PowerShell (newline, escape characters, ..)

    `0    Null
    `a    Alert
    `b    Backspace
    `f    Form feed
    `n    New line
    `r    Carriage return
    `t    Horizontal tab
    `v    Vertical tab
