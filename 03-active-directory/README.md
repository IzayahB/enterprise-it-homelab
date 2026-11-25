# 03 - Active Directory Setup On Windows Server
## Objective
Deploy Active Directory for Apex Solutions
## Environment	
Windows Server 2025, DC01, 10.10.10.10
## Domain configuration
ad.apex.test, new forest, DNS, Global Catalog
## DNS verification	
Successful A, PTR and LDAP SRV queries
## Troubleshooting
Initial DNS timeouts and reverse lookup failure
## Resolution
Created reverse lookup zone and PTR record
## Verification	
Successful Resolve-DnsName and dcdiag tests
## Screenshots

### Active Directory Domain
![Active Directory Domain](screenshots/ad-domain.png)

### DNS Forward Lookup Zone
![Forward DNS](screenshots/dns-forward.png)

### DNS Reverse Lookup Zone
![Reverse DNS](screenshots/dns-reverse.png)

### DNS Verification
![DNS Verification](screenshots/dns-verification.png)

### Forest and Domain Functional Levels
![Functional Levels](screenshots/functional-levels.png)
## Next steps
OUs, user accounts, security groups and Group Policy
