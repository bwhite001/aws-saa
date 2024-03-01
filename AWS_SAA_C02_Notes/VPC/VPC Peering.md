Privately connect two VPCs
make them behave as if they are in the same network
must not have overlapping [[CIDR]]
not transitive - every VPC that connects must have the peering enabled with each other

dont forget to update the route tables

can peer with [[VPC]]s from different accounts and [[Region]]s
we can reference a security group in a peered VPC
