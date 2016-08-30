# plesk-firewall

## Overview

If you have any problems enabling or editing the plesk firewall rule sets, then use this script instead. Deactivate the firewall in your plesk backend before you execute this script. Any new changes can be made through the new "firewall-custom.sh". Add custom rule sets in "firewall-custom.sh" (optional).

### How to install

1. Copy the script "firewall-custom.sh" preferably to /usr/local/psa/var/modules/firewall/

2. Give the script execute rights: `chmod 700 /usr/local/psa/var/modules/firewall/firewall-custom.sh`

3. Execute the script with `bash /usr/local/psa/var/modules/firewall/firewall-custom.sh`

4. Open crontab: `crontab -e`

5. And add the following line: `@reboot bash /usr/local/psa/var/modules/firewall/firewall-custom.sh`

*(alternatively you can use systemd & inotify (normally preferred, but a bit more complex)*

------

The Git Way (if you have git installed and configured on your server):

1. `cd /usr/local/psa/var/modules/firewall`

2. `git clone https://github.com/iocron/plesk-firewall.git`

3. `chmod 700 /usr/local/psa/var/modules/firewall/firewall-custom.sh` 

4. `bash /usr/local/psa/var/modules/firewall/plesk-firewall/firewall-custom.sh`

5. Open crontab: `crontab -e`

6. And add the following line: `@reboot bash /usr/local/psa/var/modules/firewall/plesk-firewall/firewall-custom.sh`

### Plesk default iptables rule sets

- Parallels Customer & Business Manager Zahlungsgateways (ACCEPT)
- Parallels Single Sign-On (ACCEPT)
- Installationsprogramm für Parallels Produkte (ACCEPT)
- Plesk-Verwaltungsoberfläche (ACCEPT)
- WWW-Server (ACCEPT)
- FTP-Server (ACCEPT)
- SSH-Server (Secure-Shell-Server) (ACCEPT)
- SMTP-Server (Übermittlungsport) (ACCEPT)
- SMTP-Server (für E-Mail-Versand) (ACCEPT)
- POP3-Server (für E-Mail-Empfang) (ACCEPT)
- IMAP-Server (für E-Mail-Empfang) (ACCEPT)
- Passwortänderungsdienst für E-Mail (ACCEPT)
- MySQL-Server (ACCEPT)
- PostgreSQL-Server (ACCEPT)
- Tomcat-Verwaltungsoberfläche (ACCEPT)
- Samba (Dateifreigabe in Windows-Netzwerken) (ACCEPT)
- Plesk-VPN (ACCEPT)
- Domainnamenserver (ACCEPT)
- IPv6 Neighbor Discovery (ACCEPT)
- Ping-Dienst (ACCEPT)
- Systemrichtlinie für eingehenden Traffic (DROP)
- Systemrichtlinie für ausgehenden Traffic (ACCEPT)
- Systemrichtlinie zur Weiterleitung von Traffic (DROP)