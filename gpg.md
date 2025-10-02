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

(Optional) If you have a subkey:

    # Enter edit mode again as before

    gpg> key 1
    gpg> expire
    gpg> 1y
    gpg> trust
    gpg> 5
    gpg> save

Print the new public key.

    gpg --armor --export KEYID

### export private key

    gpg --output private.pgp --armor --export-secret-key username@email

### import private key

    gpg --import private.pgp

### export public key

    gpg --output public.pgp --armor --export username@email
