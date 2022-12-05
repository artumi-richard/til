# ZFS on USB

It's slow... But that's the USB doing it I think. Otherwise it seems
to work.

If you want to turn off the USB you need to do an export on all the
zfs pools. 

This will export all pools

```
zfs export -a
```

Then you can turn off your USB dock. 

When you turn on the usb dock again you will need to wait a few
moments for everything to register then do 


```
zfs import -a
```

To mount encrypted volumes you will need to do 

``` 
zfs load-key -r pool/volume
// enter your password
zfs mount pool/volume
```
