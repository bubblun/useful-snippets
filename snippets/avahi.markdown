# Avahi

## Advertising Linux Services via Avahi/Bonjour

*/etc/avahi/services/multi.service:*

```xml
<?xml version="1.0" standalone='no'?><!--*-nxml-*-->
<!DOCTYPE service-group SYSTEM "avahi-service.dtd">
<service-group>
<name replace-wildcards="yes">%h</name>
<service>
<type>_afpovertcp._tcp</type>
<port>548</port>
</service>
<service>
<type>_smb._tcp</type>
<port>139</port>
</service>
<service>
<type>_rfb._tcp</type>
<port>5901</port>
</service>
<service>
<type>_device-info._tcp</type>
<port>0</port>
<txt-record>model=RackMac</txt-record>
</service>
<service>
<type>_http._tcp</type>
<port>80</port>
</service>
<service>
<type>_ssh._tcp</type>
<port>22</port>
</service>
<service>
<type>_sftp-ssh._tcp</type>
<port>22</port>
</service>
</service-group>
```
