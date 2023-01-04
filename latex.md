# cheatsheet for latex

### make hyperlink URLs work

    \usepackage[hyphens,spaces,obeyspaces]{url}
    \usepackage[hidelinks]{hyperref}

### set page width margin

    \usepackage[margin=2.5cm]{geometry}

### code blocks

Environment:

    \begin{verbatim}
        $ echo hello world
    \end{verbatim}

Inline:

    \verb|$ echo hello world|

### clear biber cache

    sudo rm -r `biber --cache`
