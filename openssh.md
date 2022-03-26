# cheatsheet for openssh

### change passphrase of private ssh key

    ssh-keygen -p

### change comment of private ssh key

    ssh-keygen -c -C "my_new_comment_e.g. username@hostname" -f ~/.ssh/id_rsa
