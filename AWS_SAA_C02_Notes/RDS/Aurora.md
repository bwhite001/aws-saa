1. proprietary
2. compatible with Postgres or MySQL
3. AWS cloud optimized - 5 times of MySQL and 3 times of Postgres
4. Automatically grows from 10GB upto 128TB
5.  has 15 replicas while MYSQL has 5 . Replication process takes 10ms
6.  Failover is instantaneous. Its HA native
7.  Storage is striped across 100s of volumes.

6 copies of data across 3 [[Availabilty Zone]]s
4 / 6 - write
3/ 6 - read
self healing with peer to peer

One instance will be Master and will write if one writer config is chosen. Automated failover will take less than 30 Seconds.

Master + 15 read replicas serve reads


Support cross [[Region]] replication

On a DB cluster load balancing happens at the connection level not in the statement level.

Backtrack  - restore data at any point of time without using backups.

Auto Scaling - horizontal scaling based on load
Custom endpoint - choosing an endpoint based on system capabilities.

Server less - unpredictable workload. - pay per second

Multi master - all nodes can write

Global Aurora - Cross Region Read Replicas - recommended

Machine Learning - SageMaker, Comprehend



