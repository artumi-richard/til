# Creating a volume

This is how you create a volume with encryption

```
zfs create -o encryption=on -o keylocation=prompt -o keyformat=passphrase tank/volumename
```
