Redis or MemCached
Cache Invalidation strategy
Can store user session

Redis - Multi [[Availabilty Zone]], backup restore, Read replicas, HA, persistent
Memecached - Multi node for partitioning , No replication, no backup and restore, multi threaded , non persistent, can afford to loose data, high performance

Do not support [[IAM]] authentication. IAM policies are only used for AWS API level security.

REDIS AUTH - can setup a token during creation, supports SSL
Memecached - suppoer SASL based authentication.

Lazyloading - all the read data is cached
write through - write when data is requested
Session store

Redis use case - leader board

**Important ports:**

-   FTP: 21
    
-   SSH: 22
    
-   SFTP: 22 (same as SSH)
    
-   HTTP: 80
    
-   HTTPS: 443
    

**vs RDS Databases ports:**

-   PostgreSQL: 5432
    
-   MySQL: 3306
    
-   Oracle RDS: 1521
    
-   MSSQL Server: 1433
    
-   MariaDB: 3306 (same as MySQL)
    
-   Aurora: 5432 (if PostgreSQL compatible) or 3306 (if MySQL compatible)