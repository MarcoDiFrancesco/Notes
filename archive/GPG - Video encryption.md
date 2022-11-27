# GPG - Video encryption
Replaced by 7zip with password

## File enctyption
7zip on Windows does not support files enctypted with OpenSSL

GPG vs OpenSSL, at the end GPG is used: [link](https://stackoverflow.com/questions/28247821/openssl-vs-gpg-for-encrypting-off-site-backups)

### Setup
`gpg --full-gen-key` to generate a new key

`gpg --armor --export marcodifran@gmail.com > key.pub` to export key in ascii

Public key is placed in *~/.config/gnupg/key.pub*

`gpg --armor --export-secret-key marcodifran@gmail.com > private.pgp` to export 

`gpg --import key.pub` to import the key, also if it is in ascii format, this will import also the Name, Comment and Email of the person that created this key

### Usage

`gpg --recipient marcodifran@gmail.com --encrypt file` creates a binary called *file.gpg* in the same folder*.* --armor in this case would encode the file in ascii, useful in case it's not possibile to transfer a binary into the network. --output file.gpg to specify output file

`gpg --decrypt file.gpg > file` decrypt file.gpg into file, it does not require the key specified in the command becuase the file already contains who owns the file
