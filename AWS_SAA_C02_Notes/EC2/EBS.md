Elastic block store

Network Drive - latency is inherent
can persist data even after [[EC2]] termination
can only be mounted to one instance at a time
Bound to an [[Availabilty Zone]] not a [[Region Scoped Service]]
free tier gives 30GB
can be re attached to other EC2 instance within an [[Availabilty Zone]]
to move across [[Availabilty Zone]]s, we have to snapshot it

*Delete on termination* flag will be false by default for additional EBS volumes.
It will be true for root volumes.
Default EBS volumes are called root volumes and there will be one when an EC2 is created.

[[EBS Snapshots]]

[[EBS Volume Types]]

Encryption is optional and uses keys from KMS ??? (AES-256)

we can copy an un-encrypted snapshot with encryption 
