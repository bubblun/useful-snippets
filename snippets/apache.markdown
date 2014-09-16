# Apache

## Remove version info from output

*/etc/apache2/apache2.conf:*

```apache
ServerSignature Off
ServerTokens Prod
```

## Using php5-fpm

Install `apache2-mpm-worker`:

```bash
apt-get install apache2-mpm-worker
```

Apache's default document root is `/var/www` on Ubuntu, and the configuration file is `/etc/apache2/apache2.conf`. Additional configurations are stored in subdirectories of the `/etc/apache2` directory such as `/etc/apache2/mods-enabled` (for Apache modules), `/etc/apache2/sites-enabled` (for virtual hosts), and `/etc/apache2/conf.d`.

Install `mod_fastcgi module`:

```bash
apt-get install libapache2-mod-fastcgi php5-fpm php5
a2enmod actions fastcgi alias
```

Add to `/etc/apache2/conf.d/php5-fpm.conf`:

```apache
<IfModule mod_fastcgi.c>
    AddHandler php5-fcgi .php
    Action php5-fcgi /php5-fcgi
    Alias /php5-fcgi /usr/lib/cgi-bin/php5-fcgi
    FastCgiExternalServer /usr/lib/cgi-bin/php5-fcgi -host 127.0.0.1:9000 -pass-header Authorization
</IfModule>
```

Restart Apache:

```bash
service apache2 restart
```
