# Troubleshooting — Active Directory DNS Resolution

## Problem

After promoting DC01 to a domain controller, DNS queries reported timeouts. A reverse DNS lookup also failed.

## Investigation

- Queried Active Directory LDAP SRV records using `nslookup`.
- Confirmed the SRV record referenced `dc01.ad.apex.test` at `10.10.10.10`.
- Verified forward DNS resolution using `Resolve-DnsName`.
- Identified that reverse DNS resolution returned a server failure.

## Resolution

Created an IPv4 reverse lookup zone for `10.10.10.0/24` and configured a PTR record mapping `10.10.10.10` to `dc01.ad.apex.test`.

## Verification

- Forward DNS resolution succeeded.
- Reverse DNS returned the correct hostname.
- Active Directory LDAP SRV records resolved successfully.
- `Resolve-DnsName` SRV lookup passed.
- `dcdiag /test:DNS /DnsBasic` passed.

An intermittent timeout remained in the `nslookup` output, although the DNS record was returned successfully. This has not yet been fully explained.

## Lessons Learned

- The difference between forward and reverse DNS.
- How A, PTR and SRV records serve different purposes.
- Why Active Directory depends on DNS for domain controller discovery.
- How to use PowerShell and Windows diagnostic utilities to investigate DNS problems.
