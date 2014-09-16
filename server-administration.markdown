# Server Administration (Ubuntu 14.04 LTS)

## fstab

### Skip waiting for unavailable volumes

Use `nobootwait`.

*/etc/fstab:*

    UUID=1234567890 /share ext4 utf8,auto,rw,user,nobootwait 0 0

## grub

### Boot without manual interruption

*/etc/defaults/grub:*

    GRUB_RECORDFAIL_TIMEOUT=0

Afterwards run `update-grub2`.

## Services

### Disable Apparmor

    update-rc.d apparmor disable
    /etc/init.d/apparmor stop
    update-rc.d -f apparmor remove
