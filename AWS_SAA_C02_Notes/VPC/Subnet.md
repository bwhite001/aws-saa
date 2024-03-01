Subnet comes under a VPC
AWS reserves 5 ip address in each subnet - first 4 and last 1
which is non usable
If one need 29 IP address, one can't choose /27 ?
32-27 = 5 ; 2^5 = 32; 32 ip address in total; 32-29 = 3 but 5 is already reserved.

IGW - Internet Gateway  - allow resources in VPC to connect to internet

![[Route Tables.png]]

*Bastion Host* - ssh proxy EC2 machine- lives in public subnet connects to private EC2 instance
