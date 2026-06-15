# Zabbix drbd monitoring
Monitoring the status of drbd with Zabbix.  

> [!NOTE] 
> This template is now part of the official community-templates repository of zabbix:  
> [Github - Zabbix/community-templates/drbd](https://github.com/zabbix/community-templates/tree/main/Applications/template_drbd/6.0)

## Description
This template has two versions, one for DRBD < version 9.x and a new for DRBD > version 9.x.
* older than Version 9.x: [zabbix-old-version](https://github.com/thetorminal/zabbix-drbd/tree/main/drbd-old-version)
  * Shows warning if the primary DRBD host becomes secondary or the secondary goes offline.  
  * The `/proc/drbd` file in the Linux system is read for this purpose.  
* newer than version 9.x: [zabbix-new-version](https://github.com/thetorminal/zabbix-drbd/tree/main/drbd-new-version)
  * Shows warning if:
    * Host is no longer Primary
    * Local disk is not UpToDate
    * Peer is not Secondary (connection problem)
    * Replication not established
  * Reads the content of the `drbdadm status` command.

Tested with:  
* Zabbix Server 6 & Zabbix Server 7
* zabbix-agent2
* DRBD 8.x (on Debian 12 server)
* DRBD 9.x (on Debian 12 server)

> [!IMPORTANT]
> **Please read the README.md** in the folder of the version you need for further **installation instructions.**

## Version History
* 1.0
    * added new version for DRBD > version 9.x
    * added more warnings for DRBD > version 9.x
    * restructured repository and README
* 0.1
    * Initial Release
