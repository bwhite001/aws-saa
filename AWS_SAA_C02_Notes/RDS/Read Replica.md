Scale the reads. should only used for SELECT operations
can create within [[Availabilty Zone]] cross [[Availabilty Zone]] or cross [[Region]]
Replication is ASYNC or eventual consistent
can be promoted as its own DB

Usually used for reporting apps

No fee for same [[Region]] but for cross [[Region]]

Read Replicas can be setup as Multi [[Availabilty Zone]] for disaster recovery

Read Replicas add new endpoints with their own DNS name. We need to change our application to reference them individually to balance the read load.

Maximun 15 read replicas

You can not create encrypted Read Replicas from an unencrypted RDS DB instance.
