Hello, world!

Signing a file:

```
jookia@titan:~/gitsshkey% ssh-keygen -Y sign -n file -f ~/.ssh/id_ed25519_sk_solo -I 'jookia' TEST_FILE
Signing file TEST_FILE
Enter PIN for ED25519-SK key: 
Confirm user presence for key ED25519-SK SHA256:/gEvgms/9HpbgpcH+K7O4GYXmqkP7siJx9zHeEWRZTg
TEST_FILE.sig already exists.
```

Verifying a file:

```
jookia@titan:~/gitsshkey% cat allowed_signers
jookia sk-ssh-ed25519@openssh.com AAAAGnNrLXNzaC1lZDI1NTE5QG9wZW5zc2guY29tAAAAID7OzA3dl0YNrkRPXGldZTzz3rtFcyBvXz661ZmMgIS3AAAABHNzaDo= jookia@titan
jookia@titan:~/gitsshkey% ssh-keygen -Y verify -n file -f allowed_signers -s TEST_FILE.sig -I 'jookia' < TEST_FILE
Good "file" signature for jookia with ED25519-SK key SHA256:/gEvgms/9HpbgpcH+K7O4GYXmqkP7siJx9zHeEWRZTg
```
