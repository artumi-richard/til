# Create ZFS pool

This creates a pool called tank

```
zfs create tank raidz /dev/sda /dev/sdb /dev/sdc
```

If you have heavy write loads an l2arc log is a good idea. If you have
heavy read loads then a Zil log is a good idea. But for most people it
will just add contention to the IO, and the linux buffers will do a
good job

No mention of encryption here as it's done at the volume level

