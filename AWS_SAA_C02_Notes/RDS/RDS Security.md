1. At rest - encrypt master and read replicas with AWS KMS - AES 256, has to be defined at launch time, if the master is not encrypted read replicas cannot be encrypted, Transparent data encryption is available for oracle and sql server.
2. in flight -  SSL, can enforce -specific to the db type

If the DB encrypted snapshot will be encrypted.
If the DB un encrypted the snapshot will be un encrypted.
can apply encryption while copying a snapshot.

*Network Security*
1. Make sure RDS deployed in private subnet not public.
2. It uses [[Security Group]]s for access management.

*Access Management*
1. [[IAM]] policies
2.  Traditional username and password
3.  [[IAM]] based authentication - only with MySQL and PostgreSQL - based on token with 15 mins life




