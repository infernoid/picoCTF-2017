## keyz [20 Points]

While webshells are nice, it'd be nice to be able to login directly. To do so, please add your own public key to ~/.ssh/authorized_keys, using the webshell. Make sure to copy it correctly! The key is in the ssh banner, displayed when you login remotely with ssh, to shell2017.picoctf.com

**Hints:**

- There are plenty of tutorials out there. This one covers key generation: https://confluence.atlassian.com/bitbucketserver/creating-ssh-keys-776639788.html
- Then, use the web shell to copy/paste it, and use the appropriate tool to ssh to the server using your key

**Solution:**

Use ssh to connect to shell2017.picoctf.com
```
$ ssh shell2017.picoctf.com
Congratulations on setting up SSH key authentication!
Here is your flag: who_needs_pwords_anyways
```

**Flag:** who_needs_pwords_anyways
