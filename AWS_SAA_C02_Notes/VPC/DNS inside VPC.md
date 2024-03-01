enableDNSSupport - decides if DNS resolution from [[Route 53]] server is supported for the VPC

if it is true, it queries DNS server at 169.254.169.253 or the reserved IP address at the base of VPC IPv4 network range plus 2.

if false - set custom DNS server

enableDnsHostNames - true - default vpc
false - newly created VPC
wont do anything if enableDNSSupport=true

