# Zabbix drbd monitoring
Monitoring the status of drbd with Zabbix.  

This template is now in the official community-templates repository:  
[Github - Zabbix/community-templates/drbd](https://github.com/zabbix/community-templates/tree/main/Applications/template_drbd/6.0)

## Description
Shows warning if the primary DRBD host becomes secondary or the secondary goes offline.  
The “/proc/drbd” file in the Linux system is read for this purpose.  

Tested with:  
* Zabbix Server 6 & Zabbix Server 7
* zabbix-agent2 / drbd (on Debian 12 server)

## Getting Started
### Dependencies
* Zabbix-Server
* Host with zabbix-agent2 and drbd installed

### Installing
#### On Zabbix frontend server:  
- Download and import the template `drbd-status.yaml`  
- Assign the `Template DRBD Status` to the docker host(s) you want to monitor  

## Version History
* 0.1
    * Initial Release
