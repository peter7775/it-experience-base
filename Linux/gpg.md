Generate key: `gpg --gen-key`

View all keys: `gpg --list-keys`

Export public key:

`gpg --export -a --output [path-to-public-key].asc [email-address]`

Export secret key:

`gpg -a --export-secret-keys > [path-to-secret-key].asc`

