# Services

## Disable service

    update-rc.d -f <SERVICE> remove

## Uninstall Apparmor

```bash
update-rc.d apparmor disable
/etc/init.d/apparmor stop
update-rc.d -f apparmor remove
```
