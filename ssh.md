# ssh-keygen -o -a 100 -t ed25519 -f ~/.ssh/id_ed25519 -C "d3c0d3r@server.com"

```
    -o : Save the private-key using the new OpenSSH format rather than the PEM format. Actually, this option is implied when you specify the key type as ed25519.

    -a: It’s the numbers of KDF (Key Derivation Function) rounds. Higher numbers result in slower passphrase verification, increasing the resistance to brute-force password cracking should the private-key be stolen.

    -t: Specifies the type of key to create, in our case the Ed25519.

    -f: Specify the filename of the generated key file. If you want it to be discovered automatically by the SSH agent, it must be stored in the default `.ssh` directory within your home directory.

    -C: An option to specify a comment. It’s purely informational and can be anything. But it’s usually filled with <login>@<hostname> who generated the key.
```

Check SSH Agent:
# eval "$(ssh-agent -s)"

Add new KEY:
# ssh-add ~/.ssh/id_ed25519


# ssh -i ~/.ssh/id_ed25519 remote@198.222.111.33
