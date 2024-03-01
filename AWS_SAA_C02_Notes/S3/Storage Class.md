S3 standard - High durability across [[Availabilty Zone]], Big Data analytics, mobile and gaming apps, cdn
S3 Standard Infrequent Access - low cost, backup, disaster recovery, minimum 30 days
S3 One Zone Infrequent access - single [[Availabilty Zone]], lower cost, secondary backup, thumbnails, minimum 30 days
S3 Intelligent Tiering  - auto tiering based on access patterns, monthly fee, minimum 30 days
Glacier - low cost, backup, each item is called archive and they are stored in vaults, minimum 90 days
	Retrieval Options - Expedited(1-5minutes), Standard (3-5 hours), Bulk(5-12 hours)
Glacier Deep Archive - cheaper,  minimum 180 days
	Retrieval Options - Standard (12 hours), Bulk(48 hours)
	
*Life Cycle Rules*
Rules for moving objects between s3 storage classes

![[s3_lifecyle.png]]
Life cycle configuration is used for the automated movement of storage classes.
Eg: of rules include
1. Move objects to standard IA 60 days after creation.
2. Move to glacier after 6 months
3. Delete access log files after an year
4. delete older versions of files

*Analytics*
helps to determine life cycle configuration
Does not work for One Zone IA and Glacier
Report updated daily
24-48 for first run



