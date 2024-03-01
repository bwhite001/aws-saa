 collect, process, migrate data in and out of aws
 
 1. Snow cone - data migration, edge computing, small, 8TB, space constrained env, AWS DataSync to send data
 2. Snowball edge - data migration, edge computing, Pay per data transfer , storage optimized - 80TB, compute optimized -42 TB
 3. Snow Mobile - data migration, truck,100 petabytes

If it takes more than a week to transfer over network, use snowball devices

Physical device sent via post office


Edge devices can run EC2 Instances and AWS Lambda functions using AWS IOT greengrass

AWS Ops hub is a software used to configure the snow device

For snowball to Glacier data transfer, s3 must be used with life cycle policy.

