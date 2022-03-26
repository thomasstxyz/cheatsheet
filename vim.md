# cheatsheet for vim

### Insert line breaks

normal mode:

    gqq

visual mode:

    gq

### show word count for current buffer

    g
    ctrl+g

### remove all comment lines with vim

    :g/^\s*#/d
    :g/^\(#\|$\)/d
    :g/\v^(#|$)/d

Another way of solving this is keeping the non-commented lines:

    :g!/^[^#]/d
