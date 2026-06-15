# Zabbix DRBD > version 9.x monitoring 
Monitoring the status of DRBD > version 9.x with Zabbix.  

## Description
Shows warning if:
  * Host is no longer Primary
  * Local disk is not UpToDate
  * Peer is not Secondary (connection problem)
  * Replication not established
Reads the content of the `drbdadm status` command.

Tested with:  
* Zabbix Server 6 & Zabbix Server 7
* zabbix-agent2 / DRBD 9.x (on Debian 12 server)

## Getting Started
### Dependencies
* Zabbix-Server
* Host with zabbix-agent2 and DRBD installed

### Installing
#### On Zabbix frontend server:  
- Download and import the template `drbd9-status.yaml`  
- Assign the `Template DRBD 9.x Status` to the docker host(s) you want to monitor

#### On the DRBD Primary Node
- Add the file `drbd.conf` in the zabbix-agent2 configuration path at `/etc/zabbix/zabbix_agent2.d`
- Restart zabbix-agent2 with `systemctl restart zabbix-agent2`

Now you should be able to get warnings in Zabbix.
You can test it with switching primary and secondary node, you should get a warning after up to 10 minutes that says "Host is no longer Primary".

## Version History
* 0.1
    * Initial Release
