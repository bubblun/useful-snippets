# Use NFS

## Server

Install the NFS server package:

    apt-get install nfs-kernel-server

Add share to `/etc/exports` with following mask:

    <path>           <computer_name>(<options>)

    /srv/all         *(rw,async,no_subtree_check)
    /srv/restricted  192.168.0.0/24(rw,async,no_subtree_check)

When serving to Mac OS X clients, you need to add `insecure` to the options. The Darwin default is to assume an "insecure" port, i.e. > 1024.

    /srv/restricted  192.168.0.0/24(rw,async,no_subtree_check,insecure)

Reload export file:

    exportfs -ra

## Client

Show available mounts for a NFS server:

    showmount -e <server>

Simply mount:

    mount 192.168.0.200:/srv/all /mnt/nfs-server

For mounting at boot time, add something like this to `/etc/fstab`:

    192.168.0.200:/srv/all /mnt/nfs-server nfs rw 0 0

## Links

* <http://wiki.ubuntuusers.de/NFS>
