# cheatsheet for GPG

### extend expired key

Print your secret keys

    gpg --list-secret-keys

Edit your secret key.

    gpg --edit-key KEYID

Now in the gpg edit mode:

    gpg> expire
    gpg> 1y
    gpg> trust
    gpg> 5
    gpg> save

Print the new public key.

    gpg --armor --export KEYID
