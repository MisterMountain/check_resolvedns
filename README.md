# check_resolvedns

lately i had the idea to recreate check_dig from monitoring_plugins in powershell for linux. As powershell for linux doesnt support the DnsClient library (because this library uses Windows-APIs) i rely on the DnsClient-PS by @rmbolger - thanks fot this!

It works like any other icinga check, and is mostly compatible to check_dig.
Currently (and maybe forever) still missing are: -4 & -6 to enforce IPv4/IPv6 usage, -T for specifying the record type and -t for the timeout

pwsh ./check_resolvedns -l icinga.com -H 1.1.1.1 -a 185.233.189.200 -w 10 -c 300
DNS WARNING - 206.17ms response time (icinga.com resolved to 185.233.189.200). |time=206.17ms;10;300;0;10000

