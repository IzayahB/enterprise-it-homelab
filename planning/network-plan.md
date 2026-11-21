|Device|IP address|Purpose|
|---|---|---|
|Proxmox host|TBD|Hypervisor management|
|DC01|	10.10.10.10	|Active Directory, DNS, DHCP|
|WIN11-01|	DHCP|	Employee workstation|
|LINUX01|	10.10.10.20|	Ubuntu server|
|HELP01|	10.10.10.30|	Help-desk services|

Lab subnet: 10.10.10.0/24

Virtual bridge: vmbr1 (isolated)

Planned AD domain: ad.apex.test

DCO01 will eventually provide DHCP services to the users on vmbr1, rather than the home router
(These are the proposed configurations, not yet deployed)
