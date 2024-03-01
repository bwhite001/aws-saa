Hybrid cloud

Storage Gateways

1. File - s3 buckets are accessible using NFS and SMB protocol, Active directory authorization
2. Volume - block storage, iSCSI backed by s3
3. Tape - for tapes, virtual tape library backed by s3 and glacier

On premise data to the cloud => Storage Gateway
File access/ NFS - user auth with AD => File gateway backed by S3
Volumes/Block Storage/iSCSI => Volume gateway backed by s3+ EBS snapshots
VTL Tape/ backup with iSCSI => Tape gateway backed by s3 and glacier
No on premise virtualization => Hardware Appliance


