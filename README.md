# plesk-firewall

## Overview

If you have any problems enabling or editing the plesk firewall rule sets, then use this script instead. Deactivate the firewall in your plesk backend before you execute this script. Any new changes can be made through the new "firewall-custom.sh". Add custom rule sets in "firewall-custom.sh" (optional).

### How to install

1. Copy the script "firewall-custom.sh" preferably to /usr/local/psa/var/modules/firewall/

2. Give the script execute rights: `chmod 700 /usr/local/psa/var/modules/firewall/firewall-custom.sh`

3. Execute the script with `bash /usr/local/psa/var/modules/firewall/firewall-custom.sh`

4. Open crontab: `crontab -e`

5. And add the following line: `@reboot bash /usr/local/psa/var/modules/firewall/firewall-custom.sh` 

	*(alternatively instead of the crontab you can use systemd & inotify (normally preferred, but a bit more complex))*

##### The Git Way (if you have git installed and configured on your server):

1. `cd /usr/local/psa/var/modules/firewall`

2. `git clone https://github.com/iocron/plesk-firewall.git`

3. `chmod 700 /usr/local/psa/var/modules/firewall/plesk-firewall/firewall-custom.sh` 

4. `bash /usr/local/psa/var/modules/firewall/plesk-firewall/firewall-custom.sh`

5. Open crontab: `crontab -e`

6. And add the following line: `@reboot bash /usr/local/psa/var/modules/firewall/plesk-firewall/firewall-custom.sh`

### Plesk default iptables rule sets

- Customer & Business Manager payment gateways (ACCEPT)
- Single Sign-On (ACCEPT)
- Plesk Installer (ACCEPT)
- Plesk administrative interface (ACCEPT)
- WWW server (ACCEPT)
- FTP server (ACCEPT)
- SSH (secure shell) server (ACCEPT)
- SMTP (submission port) server (ACCEPT)
- SMTP (mail sending) server (ACCEPT)
- POP3 (mail retrieval) server (ACCEPT)
- IMAP (mail retrieval) server (ACCEPT)
- Mail password change service (ACCEPT)
- MySQL server (ACCEPT)
- PostgreSQL server (ACCEPT)
- Tomcat administrative interface (ACCEPT)
- Samba (file sharing in Windows networks) (ACCEPT)
- Plesk VPN (ACCEPT)
- Domain name server (ACCEPT)
- IPv6 Neighbor Discovery (ACCEPT)
- Ping service (ACCEPT)
- System policy for incoming traffic (DROP)
- System policy for outgoing traffic (ACCEPT)
- System policy for forwarding of traffic (DROP)