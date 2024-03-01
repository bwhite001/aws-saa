Multi [[Availabilty Zone]] DB
NoSQL
[[IAM]]
event driven programming via Dynamo DB Streams
Auto scaling

Tables, primary key, rows/items (infinite)
each row has attributes/columns and can be null
Maximum item size - 400KB
Data types are - String, Number, Binary, Boolean, Null, List, Map, String set, Number set, Binary set
 

Read write throughput management
1. Provisioned Mode
	1. need before hand planning
	2. Pay for Read capacity Units and Write capacity units
	3. we can add auto scaling
2. On Demand Mode
	1. Pay for use
	2. Expensive
	3. Great for unpredictable workloads

*Dynamo DB Accelerator* - DAX
in memory cache
microseconds latency
5 minutes TTL

[[Elastic Cache]] can store aggregation result of computations
DAX will store objects, query cache

*DynamoDB Streams*

Ordered stream of item level modifications. this can be forwareded to [[Kinesis]] data stream, [[Lambda]] etc,
Data retention for up to 24 hours. Use cases: analytics, 
insert into derivative tables, insert into [[Elastic Search]], implement cross [[Region]] replication etc

*Global Tables* - Multi [[Region]] table
two way replication, DynamoDB Streams is a pre requisite


TTL  - Auto delete after expiry date

Index - Global Secondary Index, Local Secondary Index
for querying on attributes other than primary key


Transactions - write to multi tables in one go