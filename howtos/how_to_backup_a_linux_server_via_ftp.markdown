# Backup a Linux Server to FTP
## Install Duplicity
<code>
apt-get install duplicity
</code>
## Install Duply

### Download

[Download Duply](http://duply.net/). Extract and copy `duply` into `/usr/bin`. Make sure it has execute permissions for the user you plan to run your backups with (e.g. root).

### Setup

Make a directory for the configuration files.

	mkdir /etc/duply

Create a new profile.

	duply offsite create

Make sure Duply created a conf file in `/etc/duply/offsite`.

Create a GPG key.

	gpg --gen-key

While logged in via SSH, key generation could fail _(Not enough random bytes available)_. To remedy this, open another shell and install `rngtools`:

	apt-get install rng-tools

And run:

	rngd -r /dev/urandom

If successful, you should see an output like the following:  

> gpg: /root/.gnupg/trustdb.gpg: trustdb created  
> gpg: key 525D8AF3 marked as ultimately trusted  
> public and secret key created and signed.

Make a note of the key number (here: `525D8AF3`).

Make sure the key was added to the keystore:

	gpg --list-keys

Edit the config file:

	vim /etc/duply/offsite/conf

Fill in the GPG key number and the passphrase.

Set up cronjob:

	27 4 1 * * root /usr/bin/duply offsite backup_verify_purge --force
	23 3 * * * root /usr/bin/duply offsite backup

This guide was largely lifted from a tutorial found on [trick77.com](http://trick77.com/2010/01/01/how-to-ftp-backup-a-linux-server-duply/) and a couple of other places.

* [Server Fault: gpg not enough entropy!](http://serverfault.com/questions/214605/gpg-not-enough-entropy)
* [Techie Corner: How to setup mysqldump without password in cronjob](http://www.techiecorner.com/1619/how-to-setup-mysqldump-without-password-in-cronjob/)
