# grub

## Boot without manual interruption

*/etc/defaults/grub:*

    GRUB_TIMEOUT=0
    GRUB_RECORDFAIL_TIMEOUT=0

Afterwards run `update-grub2`.
