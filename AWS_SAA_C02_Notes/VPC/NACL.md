Network Access Control List
NACL - stateless
[[Security Group]] - stateful - whatever request that was accepted in can go out
1 NACL per [[Subnet]]
Rules are numbered from 1-32766. higher precedence on lower numbers
if 100->allow and 200->Deny, the request will be allowed

default NACL will allow everything by default
use - block a specific ip at subnet level

![[NACL.png]]

[[Security Group]] supports allow rules only, but NACL support allow and deny
[[Security Group]] all rules are evaluated for traffic, NACL rules are executed based on precedence
[[Security Group]] applies to an [[EC2]] instance while NACL applies to all [[EC2]] instances under its [[Subnet]]
