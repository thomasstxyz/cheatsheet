# cheatsheet for git

### sign commits with GPG

    git config --global commit.gpgsign true
    git config --global user.signingkey B5C9.......
    git config --global alias.logs "log --show-signature"

### set default branch

    git config --global init.defaultBranch main
