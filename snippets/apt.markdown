# apt

## Error installing package

Error:

>dpkg: error processing /var/cache/apt/archives/package (--install):
>trying to overwrite 'file/dir', which is also in package other_package
>
>Errors were encountered while processing:
>/var/cache/apt/archives/package

Solution:

    dpkg -i --force-overwrite /var/cache/apt/archives/package
