# fstab

## Skip waiting for unavailable volumes

Use `nobootwait`.

*/etc/fstab:*

    UUID=1234567890 /share ext4 utf8,auto,rw,user,nobootwait 0 0
