# AWS Solutions Architect Associate with Practice Test: 


## Question 1:

 What is the purpose of S3 Server-side encryption?

- 1. Protecting database contents for RDS and DynamoDB by encrypting at the block level
- 2. Protecting data at rest by encrypting files stored on S3(Correct)
- 3. Providing block level encryption for EC2 instance store and EBS
- 4. Protecting data in transit using a VPN

*Correct Answer(s):*
 2. Protecting data at rest by encrypting files stored on S3

**Explanation:**
Server-side encryption is used to protect data at rest. Data written to S3 is encrypted as it is written to disks in the AWS data centers. When you request the data it is decrypted so that you can access it. There is no change to the user experience. Encryption is performed at the object level.   https://docs.aws.amazon.com/AmazonS3/latest/dev/UsingEncryption.html

## Question 2:

 Which feature should be used if you need to retain Write-once Read-many (WORM) data?

- 1. EBS protected disk
- 2. Glacier Vault Lock(Correct)
- 3. S3 WORM
- 4. S3 Versioning

*Correct Answer(s):*
 2. Glacier Vault Lock

**Explanation:**
You can create a vault in Glacier, which acts as a container for multiple archives. This allows you to configure permissions on multiple archives at once, and can simplify management. Vaults also give you some additional management capabilities. You can create a vault access policy to protect the contained data. For example, you could create a policy that does not allow users to delete data. This could help prevent the unintentional deletion of backups or other data that must be retained long-term. You can also grant vault access to other AWS accounts. Vault Lock can be used to enforce compliance controls using a lockable policy. Once a vault has been locked the contents cannot be changed. An example is a Write Once Read Many (WORM) archive, in which you need to record events or store files that must remain unchanged for compliance purposes. But these files can still be read as often as necessary.   https://docs.aws.amazon.com/amazonglacier/latest/dev/vault-lock.html

## Question 3:

 Which statements regarding the RDS maintenance window are correct? (Choose two.)

- 1. The maintenance window is one hour long
- 2. Multi-AZ RDS can reduce the impact of maintenance(Correct)
- 3. You cannot modify the maintenance window
- 4. AWS will take RDS instances offline to perform required patches(Correct)

*Correct Answer(s):*
 2. Multi-AZ RDS can reduce the impact of maintenance4. AWS will take RDS instances offline to perform required patches

**Explanation:**
AWS will take RDS instances offline to perform required patches during the maintenance window. The maintenance window is 30 minutes, and you can configure when it occurs. Multi-AZ RDS can reduce the impact of maintenance because the maintenance can be performed on the standby instance, and the DB can be failed over before maintenance is performed on the primary.  https://aws.amazon.com/rds/faqs/

## Question 4:

 Can EC2 Cluster Placement Groups be used to improve network performance of VMs in multiple Availability Zones (AZ)?

- 1. Yes, but only if VPC peering is configured
- 2. Yes, as long as the AZs are in the same region.
- 3. No, placement groups do not improve network performance.
- 4. No, placement groups can only exist within a single AZ.(Correct)

*Correct Answer(s):*
 4. No, placement groups can only exist within a single AZ.

**Explanation:**
Cluster placement groups are used to provide low network latency and high throughput to a group of instances. Cluster placement groups can only exist within a single Availability Zone. The maximum network performance can be achieved by using an instance type that supports enhanced networking features such as SR-IOV. The instance type should be one that supports either 10 or 20 Gbps. All instances in the placement group should be the same type. There is no charge for creating a placement group. A spread placement group can span multiple Availability Zones.  https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/placement-groups.html

## Question 5:

 You have created an EC2 instance in a VPC, and want to apply some security controls to it. This instance is part of a group of application servers that are protected by a security group called "AppServersSG". You want to apply this existing security group, along with a new security group specially built for this application called "TopSecretSG". Which statements regarding this configuration are correct? (Choose two.)

- 1. Security groups block all traffic in both directions by default.
- 2. Security groups allow all outbound traffic by default.(Correct)
- 3. Security groups are stateful in nature, and will dynamically allow return traffic, even if an inbound rule does not exist.(Correct)
- 4. A maximum of 2 security groups can be applied to an instance.

*Correct Answer(s):*
 2. Security groups allow all outbound traffic by default.3. Security groups are stateful in nature, and will dynamically allow return traffic, even if an inbound rule does not exist.

**Explanation:**
You can use security groups to create a virtual firewall that can be applied across multiple instances. Rules are configured to control inbound and outbound traffic. You can apply up to 5 security groups to an instance running in a VPC. Think of it as attaching a firewall directly to the interface of an instance. The rules are only applied to the instances that are actually associated with the security group. There may be other instances in the same subnet that do not have the security group applied. Any changes made to the security group are immediately enforced on all instances that are assigned to the security group. The VPC also has a default security group that is automatically assigned to instances.

## Question 6:

 You need to create a managed Hadoop framework in AWS. Which service should you use?

- 1. EMR(Correct)
- 2. ElasticHPC
- 3. Redshift
- 4. DyanmoHadoop
- 5. RDS

*Correct Answer(s):*
 1. EMR

**Explanation:**
Amazon Elastic Map Reduce (EMR) provides a managed Hadoop framework that makes it easy, fast, and cost-effective to process vast amounts of data across dynamically scalable Amazon EC2 instances.   https://aws.amazon.com/emr/

## Question 7:

 What are the minimum and maximum object sizes for S3?

- 1. 0 bytes to 5 TB(Correct)
- 2. 1 byte to 5 TB
- 3. 0 bytes to 5 GB
- 4. 1 byte to 5 GB

*Correct Answer(s):*
 1. 0 bytes to 5 TB

**Explanation:**
S3 objects can range in size from a minimum of 0 bytes to a maximum of 5 terabytes. Objects up to 5 GB can be uploaded in a single PUT operation. Multipart upload can be used for larger objects to improve upload performance.  https://aws.amazon.com/s3/faqs/

## Question 8:

 Which services on AWS allow you root/admin access to the operating system?

- 1. DynamoDB, Elastic MapReduce, RDS, EC2
- 2. DynamoDB, Elastic MapReduce, OpsWorks, EC2
- 3. Elastic Beanstalk, Elastic MapReduce, OpsWorks, EC2(Correct)
- 4. Elastic Beanstalk, Glacier, OpsWorks, S3

*Correct Answer(s):*
 3. Elastic Beanstalk, Elastic MapReduce, OpsWorks, EC2

**Explanation:**
Root access is allowed for Elastic Beanstalk, Elastic MapReduce, OpsWorks, and EC2. AWS Managed services, such as S3, DynamoDB, and RDS do not allow root access to the operating system. AWS manages the patching and O.S. maintenance tasks for these services.  http://jayendrapatil.com/aws-root-access-enabled-services/

## Question 9:

 You have multiple instances associated with the same security group. What happens if you add a rule to the security group?

- 1. It is applied to all instances that are associated with the security group within 5 minutes.
- 2. It is applied to the subnet immediately.
- 3. It is applied to the instances that you specify immediately.
- 4. It is applied to all instances that are associated with the security group immediately.(Correct)

*Correct Answer(s):*
 4. It is applied to all instances that are associated with the security group immediately.

**Explanation:**
Any changes made to the security group are immediately enforced on all instances that are assigned to the security group. You can use security groups to create a virtual firewall that can be applied across multiple instances. Rules are configured to control inbound and outbound traffic. You can apply up to 5 security groups to a network interface.  https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/using-network-security.html

## Question 10:

 Your company produces bike helmets with many tech gadgets embedded. You need to provide the ability to perform both human and automated assessments of the performance of all the gadgets in the helmet. The instances that you use to perform assessments require GPUs with CUDA and low latency networking. You also must coordinate many tasks that occur across multiple applications. Which option meets these requirements?

- 1. AWS Data Pipeline with an auto-scaling group of G2 instances in a placement group
- 2. Use Amazon Simple Workflow (SWF) with an auto-scaling group of C3 instances with SR-IOV (Single Root I/O Virtualization)
- 3. AWS Data Pipeline with an auto-scaling group of C3 EC2 instances with SR-IOV
- 4. Amazon Simple Workflow (SWF) with an auto-scaling group of G2 instances in a placement group(Correct)

*Correct Answer(s):*
 4. Amazon Simple Workflow (SWF) with an auto-scaling group of G2 instances in a placement group

**Explanation:**
G2 instances should be used because they are optimized for graphics-intensive applications. G2 instances feature high-performance NVIDIA GPUs, each with 1,536 CUDA cores and 4GB of video memory. Simple Workflow Service (SWF) is a great way to coordinate many tasks that occur across multiple applications. It provides full control over tasks, including tracking their progress and maintaining their state. It can automatically recover and retry a task if it fails. This allows developers to focus on application functionality instead of managing the infrastructure plumbing.

## Question 11:

 A group of EC2 instances contain sensitive data on unencrypted EBS volumes. These instnaces need to be encrypted, along with any other new instances that are created in the future. Which EBS encryption options will accomplish these goals? (Select TWO.)

- 1. Enable encryption by default(Correct)
- 2. Encrypt the exsiting volumes using snapshots(Correct)
- 3. Configure encryption for the entire VPC
- 4. Enable encryption on the existing volumes on the fly

*Correct Answer(s):*
 1. Enable encryption by default2. Encrypt the exsiting volumes using snapshots

**Explanation:**
Encryption by default automatically encrypts new Elastic Block Store (EBS) volumes as new instances are launched within a specified region.

## Question 12:

 You want to configure your AWS account to send an email, a text message, and push a message to an SQS queue when a certain event occurs. What should you configure that can accomplish this?

- 1. SWF
- 2. SNS Topic(Correct)
- 3. CloudTrail Log
- 4. CloudFormation Template

*Correct Answer(s):*
 2. SNS Topic

**Explanation:**
Amazon Simple Notification Service (Amazon SNS) is cloud based push notification service. It can send individual messages, or send to many recipients. Push notifications can be sent to mobile device users and email recipients. You can even push messages to other distributed services. SNS is compatible with Apple, Google, Fire OS, and Windows devices, as well as any HTTP endpoint.

## Question 13:

 Which statements regarding enhanced networking are correct? (Choose two.)

- 1. Enhanced networking is supported on both Windows and Linux instances. (Correct)
- 2. Enhanced networking is supported on Linux instances only.
- 3. ParaVirtual AMIs will enable enhanced features and out-perform HVM instances.
- 4. There is an additional charge for enhanced networking.
- 5. Instances must be in a VPC to enable enhanced networking. (Correct)

*Correct Answer(s):*
 1. Enhanced networking is supported on both Windows and Linux instances. 5. Instances must be in a VPC to enable enhanced networking. 

**Explanation:**
Enhanced networking uses single root I/O virtualization (SR-IOV) to provide high-performance networking capabilities on supported instance types. SR-IOV provides higher I/O performance and lower CPU utilization when compared to traditional virtualized network interfaces. Enhanced networking provides higher bandwidth, higher packet per second (PPS) performance, and consistently lower inter-instance latencies. There is no additional charge for using enhanced networking. Enhanced networking is supported on both Windows and Linux instances. Instances must be in a VPC to enable this feature.  https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/enhanced-networking.html

## Question 14:

 How can you utilize read replicas to distribute RDS workload across multiple instances?

- 1. Use an Elastic Load Balancer to distribute traffic across RDS read replicas
- 2. Configure DB clients manually to point queries to the Read Replicas.(Correct)
- 3. Use an EC2 Auto Scaling group to automatically create and terminate read replicas

*Correct Answer(s):*
 2. Configure DB clients manually to point queries to the Read Replicas.

**Explanation:**
You can improve performance by routing read operations from DB clients to the read replica. Read replicas also provide enhanced availability because they can be spread across multiple regions. If the Master DB instance fails, a read replica can be promoted to master.

## Question 15:

 Which service is used to create users, groups, and policies to control access to AWS resources?

- 1. Web Application Firewall
- 2. AWS Directory Service
- 3. CloudWatch
- 4. IAM(Correct)

*Correct Answer(s):*
 4. IAM

**Explanation:**
Identity and Access Management (IAM) is used to control users groups, and roles within AWS. This is ideal for organizations that have multiple users and systems in the AWS cloud. Within IAM you can set password retention policies, and configure mutli-factor authentication. You can even create fine grained access control rules, such as the time of day a user can access a resource, or acceptable source IPs. You can also enable mobile applications to securely access AWS resources. IAM can be integrated with existing Active Directory installations. IAM Groups can be used to simplify user management. Groups should relate to job functions, such as administrators, developers, helpdesk, etc. You will then assign permissions to each group, and pick which users are members of each group. This makes it easy to change permissions for everyone in a group quickly and easily.   https://aws.amazon.com/iam/

## Question 16:

 You want to create a network interface that you can detach from an instance, and attach to another if needed. The IP and MAC addresses must migrate without changes.

- 1. EBS
- 2. EDI
- 3. ENI(Correct)
- 4. EIP

*Correct Answer(s):*
 3. ENI

**Explanation:**
Elastic network interfaces (ENI) can be attached to an instance in a VPC. The ENI will have one or more IPv4 or IPv6 addresses and a MAC address. ENIs can be created and attached to an instance. They can also be detached from an instance and subsequently attached to another instance. You cannot detach the primary (eth0) interface.  https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/using-eni.html

## Question 17:

 Which statements regarding RDS backups are correct? (Choose two.)

- 1. Manual Snapshots are automatically deleted when you terminate an RDS instance.
- 2. Automatic Backups are retained even after you terminate an RDS instance.
- 3. Automatic Backups are automatically deleted when you terminate an RDS insta(Correct)
- 4. Manual Snapshots are retained even after you terminate an RDS instance.(Correct)

*Correct Answer(s):*
 3. Automatic Backups are automatically deleted when you terminate an RDS insta4. Manual Snapshots are retained even after you terminate an RDS instance.

**Explanation:**
You can backup your DB instance manually at any time by taking a DB snaphot. This is a storage volume snapshot that backs up the entire DB instance and not just individual databases. DB snapshots are kept until you explicitly delete them, and are not deleted when you terminate an instance. Much like an automated backup, taking a snapshot causes a brief I/O suspension that typically lasting no more than a few minutes. If you have a Multi-AZ DB instance the snapshot is taken on the standby.

## Question 18:

 How can you use transfer acceleration to quickly upload content to an S3 bucket? (Choose two.)

- 1. Upload large files using a multi-part upload(Correct)
- 2. Use dedicated upload bandwidth to quickly transfer large amounts of data
- 3. Load data to an appliance and physically ship it to AWS
- 4. Upload content to a nearby CloudFront Edge location(Correct)

*Correct Answer(s):*
 1. Upload large files using a multi-part upload4. Upload content to a nearby CloudFront Edge location

**Explanation:**
Amazon S3 Transfer Acceleration provides fast, and secure transfers of files to S3 buckets. Transfer Acceleration leverages the edge locations used for CloudFront. You transfer the data to an edge location, and AWS routes the data to S3 over an optimized network path.  https://docs.aws.amazon.com/AmazonS3/latest/dev/transfer-acceleration-examples.html

## Question 19:

 Which statements regarding S3 Cross-Region Replication (CRR) are correct? (Chose two.)

- 1. Versioning must be enabled before you can turn on Cross-Region Replication(Correct)
- 2. You can replicate all the objects in a bucket or a subset of objects with a specific key name prefix, one or more object tags, or both(Correct)
- 3. When you enable cross-region replication all objects that are currently stored in the bucket will immediately begin replicating
- 4. Lifecycle management must be configured on the bucket before you can turn on Cross-Region Replication

*Correct Answer(s):*
 1. Versioning must be enabled before you can turn on Cross-Region Replication2. You can replicate all the objects in a bucket or a subset of objects with a specific key name prefix, one or more object tags, or both

**Explanation:**
When you enable Cross-Region Replication on a bucket all newly created objects within the bucket will be replicated to the destination bucket by default. Objects that existed before you added the replication configuration to the bucket will not be replicated. Versioning must be enabled, but lifecycle management is not required. You can replicate a subset of objects in the bucket by using a key name prefix. For example, you could create objects with the key name prefix HR/ (HR/team1, HR/team2, etc.) You could then configure CRR to only replicate object with the HR/ key name prefix.  https://docs.aws.amazon.com/AmazonS3/latest/user-guide/enable-crr.html

## Question 20:

 Which type of application works best with AutoScaling and Elastic Load Balancing?

- 1. Stateful
- 2. Stateless(Correct)

*Correct Answer(s):*
 2. Stateless

**Explanation:**
Stateless applications are ideal for horizontal scaling using a AutoScaling and ELB. Stateless applications do not store session data in a specific instance. In this way, instances are interchangeable. State information is often stored in a shared repository such as DynamoDB.  http://whatis.techtarget.com/definition/stateless-app

## Question 21:

 Which of the following HTTP methods are valid verbs for queries? (Choose two.)

- 1. POST(Correct)
- 2. PATCH
- 3. GET(Correct)
- 4. PUT

*Correct Answer(s):*
 1. POST3. GET

**Explanation:**
GET and POST are valid verbs for HTTP or HTTPS queries. An additional Query parameter named Action must also be specified. It is critical for the exam to understand that you must specify the Action parameter.

## Question 22:

 Which statement about VPC peering is correct?

- 1. Transitive peering is not supported(Correct)
- 2. VPCs can have overlapping addresses ranges
- 3. VPCs must be in the same account
- 4. VPCs must be in the same region

*Correct Answer(s):*
 1. Transitive peering is not supported

**Explanation:**
A VPC peering connection can be used to allow routing between two VPC instances with private IPv4 addresses. VPC peering connections are supported across accounts. They are also now support across regions. To establish a VPC Peering connection, one VPC (called the requestor VPC) will send a request to the peer VPC. The two VPCs must not have overlapping CIDR ranges. Once the peering connection is accepted you must create routes in your VPCs route table to point to the CIDR range of the peer. You may also need to modify your security groups to allow this traffic.

## Question 23:

 Which VPC component can be used to provide Internet Access to instances with Private IP addresses?

- 1. NAT Gateway(Correct)
- 2. Internet Gateway
- 3. VPC Peering
- 4. Direct Connect

*Correct Answer(s):*
 1. NAT Gateway



## Question 24:

 A Network Load Balancer is configured to perform an HTTP health check on a group of Web Server instances. What action will be taken if an target fails a health check?

- 1. The load balancer will migrate the instance to a different host
- 2. ELB will terminate the failed instance and replace it.
- 3. The load balancer will not route traffic to an instance that has failed a health check.(Correct)
- 4. ELB will try to restore the failed instance by automatically rebooting it.

*Correct Answer(s):*
 3. The load balancer will not route traffic to an instance that has failed a health check.

**Explanation:**
A Network Load Balancer will not route traffic to an instance that has failed a health check. If the health issue is resolved, the load balancer resume sending traffic to it. Network Load Balancing can be used to distribute incoming traffic across multiple EC2 instances, and other types of targets automatically. EC2 instances can be in different availability zones.  https://docs.aws.amazon.com/elasticloadbalancing/latest/network/target-group-health-checks.html

## Question 25:

 Which steps should you complete in order to enable SSL support on an RDS for SQL Server instance? (Choose two.)

- 1. Use the Microsoft Management Console (MMC) to import the certificate into Windows(Correct)
- 2. Download the foreign key from RDS at https://rds.amazonaws.com/doc/rds-ssl-ca-cert.pem
- 3. Download the private key from RDS at https://rds.amazonaws.com/doc/rds-ssl-ca-cert.pem
- 4. Download a public certificate key from RDS at https://rds.amazonaws.com/doc/rds-ssl-ca-cert.pem(Correct)

*Correct Answer(s):*
 1. Use the Microsoft Management Console (MMC) to import the certificate into Windows4. Download a public certificate key from RDS at https://rds.amazonaws.com/doc/rds-ssl-ca-cert.pem

**Explanation:**
AWS provides SSL support for RDS for SQL Server. This allows you to protect and secure your data both in transit and at rest. To enable SSL support you should download a public certificate key from RDS at https://rds.amazonaws.com/doc/rds-ssl-ca-cert.pem You will then use the Microsoft Management Console (MMC) to import the certificate into Windows.  https://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/UsingWithRDS.SSL.html

## Question 26:

 You need to modify an RDS DB instance, and want the changes to take effect immediately, rather than during the next maintenance window. Which statements regarding this scenario are correct? (Choose two.)

- 1. You can use the "Force" option to carry out the changes immediately.
- 2. You must use the AWS console to apply changes immediately.
- 3. If you want to carry out the changes immediately you can select the "Apply Immediately" option.(Correct)
- 4. Some DB modifications require a reboot.(Correct)

*Correct Answer(s):*
 3. If you want to carry out the changes immediately you can select the "Apply Immediately" option.4. Some DB modifications require a reboot.

**Explanation:**
Some DB modifications require a reboot, and may cause downtime if applied immediately. To avoid impact you can perform them during the next maintenance window. Different changes have different impacts. The link below is a great reference to help you know what to expect. If you want to carry out the changes immediately you can select the "Apply Immediately" option in the AWS Management Console, Similar options are available in the AWS CLI and the Amazon RDS API.    https://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/Overview.DBInstance.Modifying.html

## Question 27:

 Does S3 provide immediate consistency for overwrite puts and deletes?

- 1. No(Correct)
- 2. Yes

*Correct Answer(s):*
 1. No

**Explanation:**
When an object is overwritten in S3 the changes need to be replicated across three facilities. This means that it is possible that an old version of data may be read from a facility before the changes can be replicated.

## Question 28:

 You have an application that will run on an EC2 instance. You plan to continuously use this application for the next 24 months. It needs to be available 24 hours a day and can only tolerate minimal downtime as required for maintenance. Which type of instance is ideal for this application?

- 1. Spot Instance
- 2. On-Demand Instance
- 3. Lambda Function
- 4. Reserved Instance(Correct)

*Correct Answer(s):*
 4. Reserved Instance

**Explanation:**
Reserved Instances give you the opportunity to save money by making an investment in computing capacity on AWS. When used correctly they can provide huge savings, but they also come with some potential risk. A reserved instance allows you to purchase a reservation of capacity for either one or three years. Because you are committing to purchase the compute capacity for a longer term, the price is greatly reduced. Reserved instances are supported on EC2, as well as databases and the CloudFront CDN.

## Question 29:

 You need to capture web site usage data and analyze it in real time. The data should be used to dynamically change pricing and advertising strategies. Which solution should you use?

- 1. CloudWatch
- 2. Elastic Map Reduce
- 3. Redshift
- 4. Kinesis(Correct)

*Correct Answer(s):*
 4. Kinesis

**Explanation:**
You can use Amazon Kinesis Streams to collect and process data records in real time. The data collected can be used to dynamically change pricing and advertising strategies. Elastic Map Reduce (EMR) provides a managed Hadoop framework that makes it easy, fast, and cost-effective to process vast amounts of data across dynamically scalable Amazon EC2 instances. Redshift is Amazon’s data warehousing solution. It provides a fast, fully managed data warehouse that can be used to analyze all your data using your existing business intelligence tools.  https://aws.amazon.com/kinesis/data-streams/faqs/

## Question 30:

 Which of the following statements accurately describe a Customer Master Key? (Choose two.)

- 1. Each object in S3 uses a unique customer master key
- 2. A customer master key (CMKs) can be managed by Amazon or the customer.(Correct)
- 3. A customer master key (CMKs) is typically used to protect data encryption keys.(Correct)
- 4. A customer master key (CMKs) must be managed by AWS.

*Correct Answer(s):*
 2. A customer master key (CMKs) can be managed by Amazon or the customer.3. A customer master key (CMKs) is typically used to protect data encryption keys.

**Explanation:**
A customer master key (CMKs) is typically used to protect data encryption keys. Think of it as an encryption key used to protect another encryption key. CMKs can be either customer-managed or AWS-managed. The data key is used to encrypt or decrypt large amounts of data outside of the service. Each service that you have integrated with AWS KMS has a unique CMK. Think of the data key as the key to a lock that protects your actual data. If this key falls into the wrong hands it could be duplicated or used to unlock your data. So the CMK is used to protect this data key. https://docs.aws.amazon.com/kms/latest/developerguide/concepts.html

## Question 31:

 You have a three-tier application featuring instances running a Web Server, an Application Server, and a Database. You want to ensure that the instances running the Web Server are elastic and scalable. You are not concerned with the performance of network traffic. Which features should you use? (Choose three)

- 1. Placement groups
- 2. RDS in multiple availability zones
- 3. Dynamo DB
- 4. Elastic Load Balacing (ELB)(Correct)
- 5. EC2 Instance(Correct)
- 6. Auto Scaling(Correct)

*Correct Answer(s):*
 4. Elastic Load Balacing (ELB)5. EC2 Instance6. Auto Scaling

**Explanation:**
You should deploy the Web Server on an EC2 instances and configure ELB and auto-scaling. Elastic Load Balancing (ELB) can be used to distribute incoming traffic across multiple EC2 instances automatically. These instances can be in different availability zones. The ELB Classic Load Balancer is ideal for simple load balancing of traffic across multiple EC2 instances. The Application Load Balancer is ideal for more complex load balancing needs. Auto Scaling ensures that you have the proper amount of EC2 instances to handle the workload generated by your application. You will start by creating a collection of EC2 instances called an Auto Scaling group. You will specify the minimum and maximum number of instances that can exist in the Auto Scaling group. You can also specify desired number of instances. Auto Scaling will automatically launch or terminate instances based on the needs of your application. The Auto Scaling group uses a launch configuration as a template for its EC2 instances. The launch configuration specifies the AMI that should be used to create the instances. It also allows you to specify the instance type, key pair, security groups, and block device mapping for your instances.

## Question 32:

 You have a group of network administrators that need to manage on-premise machines and AWS instances. You want to allow them access to the AWS console without forcing them to log in again. You do not plan to create IAM users for these employees. Which method should you choose?

- 1. Grant federated access to AWS using a SAML 2 O identity provider (IDP)(Correct)
- 2. Use Web Identity Federation to provide temporary credentials
- 3. Grant temporary credentials for AWS using a SAML 2 O identity provider (IDP)
- 4. Use OAuth tokens to supply temporary access to specific roles

*Correct Answer(s):*
 1. Grant federated access to AWS using a SAML 2 O identity provider (IDP)

**Explanation:**
You should grant federated access to AWS using a SAML 2.0 identity provider (IDP). You can create a SAML 2.0 identity provider (IdP) that will allow you to integrate an on-site solution with AWS to provide Single Sign-On (SSO). For example, a user will sign in to an on-premise solution, such as Active Directory. Because a trust exists between Active Directory and AWS, that user does not need to sign into AWS to gain access to AWS resources. This user is referred to as a federated user. Once the IdP is created in AWS you must create one or more IAM roles. The job of this particular role is to allow your IdP to request temporary security credentials from AWS for federated users. The federated users will be able to carry out functions in AWS based on the policies assigned to the role. https://docs.aws.amazon.com/IAM/latest/UserGuide/id_roles_providers_enable-console-saml.html

## Question 33:

 You have a group of web servers running on EC2. A requests are received by the Web Servers they must be passed along to the application servers which provide the required service. You would like to decouple the web and application servers so that they do not directly communicate with each other.

- 1. SWF
- 2. S3
- 3. SQS(Correct)
- 4. SNS

*Correct Answer(s):*
 3. SQS

**Explanation:**
Simple Queue Service (SQS) is the first service ever launched on AWS. SQS is a fully managed message queuing service. The job of SQS is to store messages as they travel between applications. This makes it simple to decouple and distribute components of a cloud application. With SQS, you don’t need to manage a highly available messaging cluster of your own. And as with most AWS solutions, you only pay for what you use.

## Question 34:

 Which statements regarding Direct Connect are true? (Choose two.)

- 1. Local VLANs can be extended into the AWS Cloud.
- 2. Direct Connect enables connectivity to all Availability Zones within the nearest AWS region.(Correct)
- 3. All connections are redundant.
- 4. The Direct Connect SLA promises 99.9% uptime.(Correct)

*Correct Answer(s):*
 2. Direct Connect enables connectivity to all Availability Zones within the nearest AWS region.4. The Direct Connect SLA promises 99.9% uptime.

**Explanation:**
Direct Connect enables connectivity to all Availability Zones within the nearest AWS region. There is currently no SLA for Direct Connect. Direct Connect can be used to create a dedicated network connection between your organization and an AWS Direct Connect location. This is useful if you need a high-throughput, consistent network experience. All data transferred over this connection is charged a reduced Direct Connect data transfer rate. 1 Gbps and 10 Gbps connections are available, and multiple connections can be supported for increased bandwidth. While multiple VLANs are supported on Direct Connection, you still cannot extend a VLAN into the AWS Cloud.    https://aws.amazon.com/directconnect/faqs/

## Question 35:

 You are using EC2 to deploy a database instance that contains sensitive data. You must ensure that access to this information is properly secured. Which statements regarding this configuration are correct? (Choose two.)

- 1. You can use a Security Group to protect the instance.(Correct)
- 2. AWS does not have root level access to this instance.(Correct)
- 3. AWS will patch the Operating System.
- 4. AWS will maintain and patch the database engine.

*Correct Answer(s):*
 1. You can use a Security Group to protect the instance.2. AWS does not have root level access to this instance.

**Explanation:**
AWS does not have root level access to an EC2 instance, and will not perform any patching or maintenance. Using the Relational Database Service (RDS) instead would allow AWS to perform this maintenance. You can secure EC2 instances using a security group.   http://jayendrapatil.com/aws-root-access-enabled-services/

## Question 36:

 Which of the following describes Amazon Snowball?

- 1. AWS provides you a physical appliance that you can use to import large amounts of data to AWS(Correct)
- 2. You can use your own physical device to import large amounts of data to AWS
- 3. You can upload large amounts of data to a nearby edge location to accelerate large data imports
- 4. AWS will send a vehicle to your location that you can upload massive amounts of data to

*Correct Answer(s):*
 1. AWS provides you a physical appliance that you can use to import large amounts of data to AWS

**Explanation:**
Snowball is a secure appliance that you can use to transfer large amounts of data into AWS. It can store petabytes of data, making it extremely scalable. This can help you avoid high network costs and long transfer times associated with uploading data to AWS. It also can relieve security concerns. Snowball is easy to use. You simply create a job in the AWS Management Console and a Snowball appliance will be shipped to you. You can then attach it to your local network and use the Snowball client to select the file directories that you want to transfer to the appliance. All data on the appliance is encrypted.

## Question 37:

 You have created an RDS DB instance that is a Multi-Availability Zone (AZ) deployment and need to budget accordingly. Which statements regarding this deployment are correct? (Choose two.)

- 1. Your backup storage usage will not change when you configure a Multi-AZ RDS instance(Correct)
- 2. There is no charge for replicating data between the primary and the secondary(Correct)
- 3. Replicating data between the primary and the secondary is billed at half of the standard transfer charge
- 4. I/O requests per month will not change when you configure a Multi-AZ RDS instance

*Correct Answer(s):*
 1. Your backup storage usage will not change when you configure a Multi-AZ RDS instance2. There is no charge for replicating data between the primary and the secondary

**Explanation:**
There is no charge for replication data transfer between your primary and standby. Backup storage usage does not change when you configure a Multi-AZ RDS instance. All backups are taken from your standby so that there is no impact on the primary due to I/O suspension. Multi-AZ deployments incur more I/O requests per month because changes need to be written to the primary and standby instances. Writes on the primary are synchronously replicated to the standby. Read I/O usage is not effected because all reads are performed against a single instance.   https://aws.amazon.com/rds/pricing/

## Question 38:

 You have multiple web servers deployed as EC2 instances that serve up the same website. The instances are located in different regions. You have configured Route 53 Latency-Based Routing to reduce latency. You have also created multiple instances within each region, and placed them in different availability zones. Weighted record sets have been configured within each region. As part of a regular DR test you have disabled all instances in one region, and you notice that the requests are not automatically re-directed to the running instances in the other region. How can you resolve this issue? (Choose two.)

- 1. Configure HTTP Health Check(Correct)
- 2. Configure a higher weight for the running instances
- 3. Set "Evaluate Target Health" to "Yes" on the record sets(Correct)
- 4. Remove the Weighted record sets, because they are incompatible with latency based routing

*Correct Answer(s):*
 1. Configure HTTP Health Check3. Set "Evaluate Target Health" to "Yes" on the record sets

**Explanation:**
In this scenario the latency record sets are being used to select a region close to the requestor. The weighted record sets are being used to distribute requests across multiple instances in different availability zones within a region. You should configure HTTP Health Check. Route53 includes health checks that can be used to monitor web applications, web servers, and other resources. Route53 will submit automated requests over the Internet to your application. You can specify the frequency and interval of these requests. The health check should mirror your typical user traffic. You should set "Evaluate Target Health" to "Yes" on the record sets. This will make Route 53 evaluate the health of the weighted resource record sets and respond accordingly. Weighted record sets and latency based routing are compatible, and can be part of a valid failover design.  https://docs.aws.amazon.com/Route53/latest/DeveloperGuide/TutorialLBRMultipleEC2InRegion.html

## Question 39:

 You want to be able to migrate a static public IP address from one instance to another. You do not need to maintain the same MAC address if you move the IP to a new instance. Which AWS service should you use?

- 1. ENI
- 2. EIP(Correct)
- 3. Instance Store
- 4. EBS

*Correct Answer(s):*
 2. EIP

**Explanation:**
An Elastic IP address is a static IPv4 address that is associated with your AWS account. An Elastic IP can be attached to and detached from an EC2 instance, allowing you to mask failures. An Elastic IP address is a publicly routable IPv4 address. EC2 instances can have a public IP address without having an EIP, but the IP is dynamic and cannot be moved from one instance to another.  https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/elastic-ip-addresses-eip.html

## Question 40:

 True or False: It is possible to have multiple SQS queues with different priorities.

- 1. FALSE
- 2. TRUE(Correct)

*Correct Answer(s):*
 2. TRUE

**Explanation:**
An SQS priority queue is designed for delivering messages based on priority, not time. Different priorities can be defined per queue.    https://aws.amazon.com/sqs/details/

## Question 41:

 Which statements regarding RDS automated backups are correct? (Choose two.)

- 1. Automated backups are preserved when you delete an instance.
- 2. Retention periods can be set between 0-14 days.
- 3. Retention periods can be set between 0-35 days.(Correct)
- 4. The default retention interval is 1 day.(Correct)

*Correct Answer(s):*
 3. Retention periods can be set between 0-35 days.4. The default retention interval is 1 day.

**Explanation:**
You can use RDS Automated Backups to create a storage volume snapshot of your DB instance. This backs up the entire DB instance. You can customize the retention period from 0-35 days. The default period retention period is one day. An outage will occur if you change the backup retention period from 0 to a non-zero value or from a non-zero value to 0. Automated backups are deleted after the retention interval and cannot be recovered. When you delete a DB instance all automated backups are also deleted.   https://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/USER_WorkingWithAutomatedBackups.html

## Question 42:

 You are using AWS Direct Connect to access resources inside your AWS VPC. You want your general Internet traffic to flow over a different connection that is not associated with AWS. Which configuration tasks will accomplish this? (Choose three.)

- 1. Redistribute BGP routes from AWS into your existing routing infrastructure(Correct)
- 2. Configure a public Interface on your AWS Direct Connect link(Correct)
- 3. Configure a static route that points to Amazon S3
- 4. Create a private interface on your AWS Direct Connect link
- 5. Advertise a default route to AWS using BGP
- 6. Advertise specific networks into AWS(Correct)

*Correct Answer(s):*
 1. Redistribute BGP routes from AWS into your existing routing infrastructure2. Configure a public Interface on your AWS Direct Connect link6. Advertise specific networks into AWS

**Explanation:**
You should configure a public Interface on your AWS Direct Connect link, redistribute BGP routes from AWS into your existing routing infrastructure, and advertise specific networks into AWS. To understand this question you need to be familiar with basic routing concepts and route re-distribution. Direct Connect can be used to create a dedicated network connection between your organization and an AWS Direct Connect location. This is useful if you need a high-throughput, consistent network experience. For example, assume you have private resources on AWS. You can access them over a defined VLAN that is dedicated to private traffic. Other VLANs could be used to access resources with public IP addresses. For routing purposes, Direct Connect requires the use of the Border Gateway Protocol (BGP) with an Autonomous System Number (ASN) and IP Prefixes. This allows your routers to send the appropriate traffic to AWS, and general traffic can flow out of a normal Internet connection.   https://aws.amazon.com/directconnect/faqs/

## Question 43:

 You have created an EC2 instance and installed an application on it that will write backups to an S3 bucket. What is the ideal way to give this instance access to the S3 bucket?

- 1. Assign a Role to the EC2 instance(Correct)
- 2. Embed IAM credentials in the operating system of the instance.
- 3. Set up a VPC endpoint that allows the instance direct access to S3.

*Correct Answer(s):*
 1. Assign a Role to the EC2 instance

**Explanation:**
Applications running on an Amazon EC2 instance may need to access other AWS services. An IAM role can be used to securely provide credentials to the application. An IAM role is a set of permissions that can be applied to users or groups. IAM can provide temporary credentials to the EC2 instance, and assign the role to those temporarily assigned credentials.   https://aws.amazon.com/blogs/security/easily-replace-or-attach-an-iam-role-to-an-existing-ec2-instance-by-using-the-ec2-console/

## Question 44:

 You have a large number of high-quality MP4 videos that need to be converted to a mobile-friendly format. The original MP4 videos will not be used often, but should be stored using a low-cost option in case they are ever needed. These videos will be watched by users all over the world, and you need to ensure that they experience minimal latency. Which three solutions can accomplish these goals? (Choose three.)

- 1. Use Cloudfront to distribute the mobile-friendly formatted videos.(Correct)
- 2. Use SQS to distribute video conversion tasks across many instances.
- 3. Use Elastic Transcoder to convert MP4 videos to a mobile-friendly format(Correct)
- 4. Archive the original videos in Glacier.(Correct)
- 5. Use EBS snapshots to back up the original MP4 videos.

*Correct Answer(s):*
 1. Use Cloudfront to distribute the mobile-friendly formatted videos.3. Use Elastic Transcoder to convert MP4 videos to a mobile-friendly format4. Archive the original videos in Glacier.

**Explanation:**
You should use Elastic Transcoder to convert MP4 videos to a mobile-friendly format. You should archive the original videos in Glacier, and use Cloudfront to distribute the mobile-friendly formatted videos to Edge locations all over the world. Elastic Trascoder is a Media transcoding service in the cloud. It can be used to convert media files from a source format into another version. For example, assume you have media files that need to run on mobile devices, but are not in a mobile friendly format. Elastic transcoder can be used to change the format. Amazon Glacier provides a secure, durable, and extremely low-cost cloud storage service. Glacier is suitable for long-term archiving and backups. Data can be stored at a very low cost, ranging as low as .4 cents per gigabyte per month. CloudFront is a Content Delivery network, or CDN. CloudFront leverages edge locations that are spread across the globe to deliver websites, video content, and other web assets from the nearest edge location. This improves the overall performance of these services.

## Question 45:

 Which statements regarding NAT instances are correct? (Choose two.)

- 1. Amazon provides AMIs that are configured to run as NAT instances.(Correct)
- 2. You should disable Source/Destination check(Correct)
- 3. Port forwarding is not supported.
- 4. NAT instances are highly available.

*Correct Answer(s):*
 1. Amazon provides AMIs that are configured to run as NAT instances.2. You should disable Source/Destination check

**Explanation:**
Network Address Translation (NAT) is a widely used network standard that translates one IP address to another. AWS instances are often created with private IP addresses that are not routable on the Internet. When an instance with a private IP address needs to send traffic to the Internet, the traffic is routed to the NAT instance. The NAT instance removes the original source IP address and replaces it with the public Elastic IP (EIP) address of the NAT instance. The NAT instance keeps track of which conversation belongs to each instance by using different port numbers. Amazon provides AMIs that are configured to run as NAT instances. NAT instances are not highly available. You must use a script to manage failover between instances. NAT Gateways are a good alternative if high availability is required. EC2 instances perform source/destination checks by default. The instance will only send or receive traffic that it is the source or destination of. This will prevent the instance from forwarding traffic from other instances, which will break NAT. To resolve this issue you must disable source/destination checks on the NAT instance.   https://docs.aws.amazon.com/AmazonVPC/latest/UserGuide/VPC_NAT_Instance.html

## Question 46:

 You want to store a group of objects using an AWS solution that can tolerate the loss of two physical facilities in a way that minimizes costs. Which solution should you use?

- 1. EBS
- 2. CloudFront
- 3. S3(Correct)
- 4. Instance Store

*Correct Answer(s):*
 3. S3

**Explanation:**
S3 achieves a high level of durability by storing data on multiple devices across multiple physical facilities. S3 is commonly used to store data for analytics, backups, and disaster recovery. Amazon provides easy to use cloud data migration options to upload data to S3. S3 is object storage and cannot provide block storage.  https://aws.amazon.com/s3/details/

## Question 47:

 Which feature provides high-performance network performance on supported EC2 instances?

- 1. Traffic Shaping
- 2. Direct Connect
- 3. Network IO Control
- 4. Enhanced Networking(Correct)

*Correct Answer(s):*
 4. Enhanced Networking

**Explanation:**
Enhanced networking uses single root I/O virtualization (SR-IOV) to provide high-performance networking capabilities on supported instance types. SR-IOV is a method of device virtualization that provides higher I/O performance and lower CPU utilization when compared to traditional virtualized network interfaces. Enhanced networking provides higher bandwidth, higher packet per second (PPS) performance, and consistently lower inter-instance latencies. There is no additional charge for using enhanced networking.   https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/enhanced-networking.html

## Question 48:

 You plan to host a website using EC2. The site must be highly available and should tolerate the failure of an Availability Zone (AZ). The solution should dynamically scale based on changes in workload. Which configuration option will accomplish these goals?

- 1. Configure user data scripts to launch highly available instance types.
- 2. Create an Elastic Load Balancer (ELB) in front of an Auto-Scaling group.(Correct)
- 3. Configure a CloudFront distribution.
- 4. Create an Auto-scaling group with a minimum count of 1 instance.

*Correct Answer(s):*
 2. Create an Elastic Load Balancer (ELB) in front of an Auto-Scaling group.

**Explanation:**
You should configure a AutoScaling Group behind an Elastic Load Balancer. The AutoScaling Group should have a minimum of two instances to ensure that there is at least one instance in each Availability Zone.  https://docs.aws.amazon.com/autoscaling/ec2/userguide/autoscaling-load-balancer.html

## Question 49:

 What level of durability does S3-Infrequent Access provide?

- 1. 99.99 Percent
- 2. 99 Percent
- 3. 99.999999999 Percent(Correct)
- 4. 100 Percent

*Correct Answer(s):*
 3. 99.999999999 Percent

**Explanation:**
S3 Standard - IA offers provides 99.999999999% durability. This is the same level of durability as S3-Standard.  https://aws.amazon.com/s3/storage-classes/

## Question 50:

 What is the service level agreement for monthly uptime of EC2?

- 1. 100 Percent
- 2. 99.99 Percent(Correct)
- 3. 99.999999999 Percent
- 4. 99 Percent

*Correct Answer(s):*
 2. 99.99 Percent

**Explanation:**
AWS commits to maintaining 99.99% uptime on EBS and EC2. Failure to maintain the SLA results in AWS issuing a service credit to customers.   https://aws.amazon.com/ec2/sla/

## Question 51:

 Which statements regarding ELB Cross-zone load balancing are correct? (Choose two.)

- 1. Cross-zone load balancing is automatically enabled for a Classic Load Balancer.
- 2. Multiple AZs are not recommended when using the Classic Load Balancer.
- 3. Traffic is distributed evenly across all instances in all Availability Zones. (Correct)
- 4. Cross-zone load balancing is automatically enabled for an Application Load Balancer.(Correct)

*Correct Answer(s):*
 3. Traffic is distributed evenly across all instances in all Availability Zones. 4. Cross-zone load balancing is automatically enabled for an Application Load Balancer.

**Explanation:**
ELB can operate in either Classic Load Balancer or Application Load Balancer mode. When you enable an Availability Zone (AZ) for the load balancer an ELB node is created in that AZ. Multiple AZs are recommended when using the Classic Load Balancer. It is required for the Application Load Balancer. Cross-zone load balancing distributes traffic evenly across all registered instances in all enabled AZs. When cross-zone load balancing is disabled, each load balancer node distributes requests evenly across the registered instances in its Availability Zone only.  https://docs.aws.amazon.com/elasticloadbalancing/latest/classic/enable-disable-crosszone-lb.html

## Question 52:

 You have VPCs created in two different AWS accounts that need to be able to communicate with each other. Which service should you use?

- 1. VPC Peering(Correct)
- 2. Cross-account VPC
- 3. Direct Connect
- 4. Consolidated billing

*Correct Answer(s):*
 1. VPC Peering

**Explanation:**
A VPC peering connection can be used to allow routing between two VPC instances with private IPv4 addresses. VPC peering connections are supported across accounts within a region. To establish a VPC Peering connection, one VPC (called the requestor VPC) will send a request to the peer VPC. The two VPCs must not have overlapping CIDR ranges. Once the peering connection is accepted you must create routes in your VPCs route table to point to the CIDR range of the peer. You may also need to modify your security groups to allow this traffic.

## Question 53:

 You need a low-cost archiving option to store data that should be retained for years. You can tolerate some delay if you ever need to retrieve this data. All data should be encrypted by default. Which AWS service should you use?

- 1. EBS
- 2. S3
- 3. No AWS service provides all these features
- 4. Glacier(Correct)

*Correct Answer(s):*
 4. Glacier

**Explanation:**
Think of Amazon Glacier as an archiving service in the cloud. It provides a secure, durable, and extremely low-cost cloud storage service. Glacier is suitable for long term storage needs and as a backup repository. Glacier is largely for offline storage. Retrieving data typically takes between 3-5 hours at the standard retrieval level. The time it takes depends of the service level you choose. Expedited retrievals typically take 1-5 minutes, but are more expensive than standard. Data can be stored at a very low cost, ranging as low as .4 cents per gigabyte per month. Glacier is designed to provide 99.999999999% durability, and stores redundant copies of data in multiple datacenters. There is no maximum amount of data that you can store Glacier. A single archive can contain up to 40 TB of data.   https://aws.amazon.com/glacier/faqs/

## Question 54:

 Which statements regarding Oracle licensing on AWS are correct? (Choose two.)

- 1. You can bring your own existing licenses(Correct)
- 2. Pre-existing licenses cannot be used in AWS
- 3. You must use consistent licensing editions across Oracle instances
- 4. You can license Orace to run in AWS(Correct)

*Correct Answer(s):*
 1. You can bring your own existing licenses4. You can license Orace to run in AWS

**Explanation:**
You can bring your own pre-existing Oracle software licenses to Amazon EC2. This reduces your price per-hour of RDS instances. You can also deploy RDS instances with include Oracle licensing built-in to the per-hour price.  https://aws.amazon.com/rds/oracle/pricing/

## Question 55:

 You have stored a set of objects in an S3 bucket configured for the S3-IA storage class. Which statement regarding this is correct?

- 1. This is Reduced Redundancy Storage, which decreases the durability of your stored data.
- 2. This is Read Replica Storage, which allows you to load balance read operations across multiple S3 buckets.
- 3. This storage class provides slower performance, lower availability, and lower durability than S3 Standard.
- 4. This storage class is just as fast as S3 Standard, but should only be used for data that is not accessed frequently.(Correct)

*Correct Answer(s):*
 4. This storage class is just as fast as S3 Standard, but should only be used for data that is not accessed frequently.

**Explanation:**
S3 Standard - Infrequent Access (Standard - IA) is an S3 class that is ideal for data that is not needed very often. It is less costly per GB than S3 Standard, but still provides the same performance when you need to access data. A per GB retrieval fee is charged when data is accessed, so you should not use this tier for frequently utilized data. This tier is used long-term storage, backups, and as a data store for disaster recovery. You can have objects in the same bucket configured for either S3 Standard or S3 Infrequent Access. You can also configure a lifecycle policy to move data to S3 Standard – IA after a certain amount of time.

## Question 56:

 What is an NS record, and is it supported by Route 53? (Choose two.)

- 1. No it is not supported
- 2. NS = Name Source Record
- 3. NS = Name Server Record(Correct)
- 4. Yes it is supported(Correct)

*Correct Answer(s):*
 3. NS = Name Server Record4. Yes it is supported

**Explanation:**
When you take the exam it is important to know EXACTLY what certain acronyms stand for. NS stands for Name Server Record. These are used to delegate a subdomain to a set of name servers. For example, "If you want to know about hosts in the trainertests zone, ask the name server ns1.sample.com". NS records are supported by Route 53. For more details see the "Which DNS record types does Amazon Route 53 support?" section using the link below.  https://aws.amazon.com/route53/faqs/#which_dns_records_are_supported

## Question 57:

 You need to monitor a group of EC2 instances using CloudWatch. Some instances require more frequent monitoring than others. What are the default and minimum monitoring intervals?

- 1. 5 minutes default, 2 minutes minimum.
- 2. 15 minutes default, 1 minute minimum.
- 3. 5 minutes default, 1 minute minimum.(Correct)
- 4. 15 minutes default, 2 minutes minimum.

*Correct Answer(s):*
 3. 5 minutes default, 1 minute minimum.

**Explanation:**
EC2 instances are enabled for basic monitoring by default. This provides data in 5-minute periods at no charge. For an additional charge you can enable detailed monitoring on an instance. This provides data in 1-minute periods.   https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/viewing_metrics_with_cloudwatch.html

## Question 58:

 You are running a database in your AWS account and want to reduce costs by minimizing the activity on the RDS instance. Which service could accomplish this?

- 1. Redshift
- 2. Elasticache(Correct)
- 3. Database Sharding
- 4. Read Replica

*Correct Answer(s):*
 2. Elasticache

**Explanation:**
Elasticache makes databases perform faster and potentially at a lower cost. Elasticache provides a distributed in-memory cache in the AWS cloud. It is scalable and easy to manage. You can run ElastiCache in an Amazon Virtual Private Cloud (Amazon VPC). This allows you to configure secure network access to your clusters. You can easily scale your ElastiCache environment by adding or remove nodes, clusters, or read replicas. ElastiCache support Memcached and Redis caching engines, but of which are industry standard options. Existing applications that already use Memcached or Redis can be take advantage of ElastiCache with. You simply need to configure the host names and port numbers of the ElastiCache nodes that you have deployed. You can even use Auto Discovery with Memcached to allow your applications identify all of the nodes in a cache cluster and connect to them. This allows you to make changes to ElastiCache nodes and clusters without reconfiguring the applications.   https://aws.amazon.com/elasticache/faqs/

## Question 59:

 Which of the following methods can be used to increase the number of IOPs that an instance can handle? (Choose three.)

- 1. Configure cross-zone load balancing
- 2. Configure RAID 0(Correct)
- 3. Load balance IOPs across Availability Zones
- 4. Use an EBS-Optimized Instance(Correct)
- 5. Increase the size of the instance(Correct)

*Correct Answer(s):*
 2. Configure RAID 04. Use an EBS-Optimized Instance5. Increase the size of the instance

**Explanation:**
A single instance can have multiple EBS volumes. RAID 0 can be used to improve storage performance. Some instances can generate more IOPS than a single EBS volume can be provisioned for. Multiple gp2, io1, st1, or sc1 volumes can be joined together in a RAID 0 array, and data can be striped across these volumes. Certain instance types may experience contention between network and storage traffic. EBS-optimized instances separate the two types of traffic to prevent contention. Larger EC2 instance types provide higher maximum IOPS. See this link for details: http://docs.aws.amazon.com/AWSEC2/latest/UserGuide/EBSOptimized.html An EBS volume is local to an Availability Zone (AZ).

## Question 60:

 Which of the following is used to uniquely identify an AWS resource?

- 1. AWS Resource Tag (ART)
- 2. AWS Resource Number (ARN)
- 3. AWS Resource Name (ARN)(Correct)
- 4. AWS Record Name (ARN)

*Correct Answer(s):*
 3. AWS Resource Name (ARN)

**Explanation:**
Amazon Resource Names (ARNs) are used to uniquely identify AWS resources. Global resources, such as IAM policies, Amazon Relational Database Service (Amazon RDS) tags, and API calls must be identified with an ARN.   https://docs.aws.amazon.com/general/latest/gr/aws-arns-and-namespaces.html

## Question 61:

 You have an application that must run every night. It will pull data from an S3 bucket, process it, and write the results to a DynamoDB table.The application will run in EC2. No state information or persistent data will be stored in the EC2 instance. Which EC2 option may be a good choice to accomplish this task?

- 1. Reserved Instance
- 2. On-Demand Instance
- 3. Spot Instance(Correct)

*Correct Answer(s):*
 3. Spot Instance

**Explanation:**
EC2 Spot instances are a cost-efficient option when you need computing resources. Spot Instances allow you to bid on spare Amazon EC2 computing capacity at a discount. This can allow you to significantly reduce the cost of running your applications, and temporarily scale up your computing capacity and throughput. Amazon AWS has built up a massive amount of compute capacity all over the world. At certain times some regions may not require all of the compute capacity available. During these times the CPU resources may simply sit idle, and go unused. Spot instances enable users to take advantage of this spare CPU capacity at a low cost.

## Question 62:

 Which AWS service allows you to preserve and revert to all old versions of a file, including files that have been deleted?

- 1. S3 with Versioning(Correct)
- 2. EBS with Versioning
- 3. EBS with Snapshots
- 4. S3 with Lifecycle Management

*Correct Answer(s):*
 1. S3 with Versioning

**Explanation:**
Versioning can be used to provide restore points for objects stored in an S3 bucket. This allows you to easily recover from the accidental deletion of an object, or revert an object to an old version if unwanted changes have been made. Versioning does require additional storage space, and will therefore incur additional charges. This may be a good use case for multiple buckets. You could create a bucket for valuable objects and enable versioning, and a bucket for less critical data with versioning disabled.  https://docs.aws.amazon.com/AmazonS3/latest/dev/Versioning.html

## Question 63:

 What is required to create an S3 bucket?

- 1. An MFA device
- 2. A globally-unique name(Correct)
- 3. A Security Group
- 4. A VPC

*Correct Answer(s):*
 2. A globally-unique name

**Explanation:**
Each S3 bucket must have a globally unique name. For more, see: https://docs.aws.amazon.com/AmazonS3/latest/dev/BucketRestrictions.html

## Question 64:

 Which two types of IP addresses can be automatically assigned to an EC2 instance when you launch it within a public subnet?

- 1. A Private IP that is only reachable within the Amazon EC2 network(Correct)
- 2. A multicast address to make communications inside the VPC more efficient.
- 3. An Elastic IP that can be detached from the instance as needed.
- 4. A Public IP that is reachable from the Internet, if the security group is configured to allow it.(Correct)

*Correct Answer(s):*
 1. A Private IP that is only reachable within the Amazon EC2 network4. A Public IP that is reachable from the Internet, if the security group is configured to allow it.

**Explanation:**
An EC2 instance is created with a ​Private IP that is only reachable within the Amazon EC2 network and a public IP address.   https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/using-instance-addressing.html

## Question 65:

 Your organization has instances that need to download software from specific servers on the Internet for updates. All other outbound traffic should be blocked. Other instances exist on the same subnet and should not be restricted.  Which of the following options will accomplish this goal?

- 1. Manually configure routing tables to remove all routes not specific to the required servers.
- 2. Create a proxy server and enforce URL rules
- 3. Create an access control list and only allow outbound traffic to the required servers.
- 4. Create a security group and only allow outbound traffic to the required servers.(Correct)

*Correct Answer(s):*
 4. Create a security group and only allow outbound traffic to the required servers.

**Explanation:**
You should create a security group and block all outbound traffic other than the required servers. Manually modifying the routing tables could provide the required effect, but is much more complex and likely to create unintended consequences. A proxy server would force all the traffic to traverse an instance dedicated to this function. While this solution could potentially work, it is much more resource intensive and complex than configuring a security group.  https://docs.aws.amazon.com/AmazonVPC/latest/UserGuide/VPC_SecurityGroups.html

## Question 66:

 You have a web application running on EC2 that you would like to host in multiple regions to increase availability. Which service can you use to accomplish this?

- 1. Auto Scaling Group
- 2. Route 53 Health Checks(Correct)
- 3. Auto Recovery
- 4. Elastic Load Balancer

*Correct Answer(s):*
 2. Route 53 Health Checks

**Explanation:**
Route53 includes health checks that can be used to monitor web applications, web servers, and other resources. Route53 will submit automated requests over the Internet to your application. You can specify the frequency and interval of these requests. The health check should mirror your typical user traffic. Notifications can be generated by CloudWatch when a failed health check occurs. A good use case is when you have multiple Web Servers that are redundant. Route53 should only route traffic to Web Servers that are healthy and functioning properly. You can associate health checks with your resource DNS record sets. When a health check fails, Route53 routes traffic away from the associated resource. This is referred to as DNS failover.

## Question 67:

 What feature should be used to automatically move S3 objects to other storage classes as the objects age?

- 1. lifecycle policy(Correct)
- 2. replication
- 3. versioning
- 4. auto-tiering

*Correct Answer(s):*
 1. lifecycle policy

**Explanation:**
For more, see: https://docs.aws.amazon.com/AmazonS3/latest/dev/object-lifecycle-mgmt.html

## Question 68:

 You require a Recovery Time Objective(RTO) of 2 hours or less and a Recovery Point Objective (RPO) of 30 minutes or less for a database running on an EC2 instance in the event of an AZ failure. How should this instance be backed up to accompish these goals at the minimum cost?

- 1. Backup data to S3-IA(Correct)
- 2. Backup data to Glacier
- 3. Backup data to S3-Standard
- 4. Backup data to S3 One-Zone IA

*Correct Answer(s):*
 1. Backup data to S3-IA

**Explanation:**
The data should be backed up to S3-Infrequent Access. This will accomplish the required RPO and RTO. S3-IA is less expensive than S3 Standard. Glacier will not support the RTO. One-Zon will not protect against an AZ failure. https://aws.amazon.com/s3/storage-classes/

## Question 69:

 What is Amazon's proprietary relational database engine that is MySQL and PostgreSQL compatible?

- 1. DynamoDB
- 2. Kinesis
- 3. Redshift
- 4. Aurora(Correct)

*Correct Answer(s):*
 4. Aurora

**Explanation:**
Amazon Aurora is an Amazon proprietary relational database engine that is MySQL and PostgreSQL compatible.

## Question 70:

 Which of the following tasks can be accomplished using S3 Lifecycle Management? (Choose two.)

- 1. Automatically migrate data from Instance Store to S3.
- 2. Automatically move old data to a Glacier Archive.(Correct)
- 3. Automatically backup RDS instances to S3.
- 4. Automatically delete incomplete Multipart uploads.(Correct)

*Correct Answer(s):*
 2. Automatically move old data to a Glacier Archive.4. Automatically delete incomplete Multipart uploads.

**Explanation:**
As you add more objects to an S3 bucket the charges incurred will continue to grow. Often there are too many objects stored to manually manage. Lifecycle management can be used to store S3 objects in different tiers as they age. For example, after a year we may want objects to be automatically moved to S3 Standard - Infrequent Access. This storage class is less expensive than S3 Standard for less-frequently used data. Objects can be automatically archived to Glacier, which reduces the costs even further. https://aws.amazon.com/blogs/aws/s3-lifecycle-management-update-support-for-multipart-uploads-and-delete-markers/

## Question 71:

 You are running a group of web servers behind an Elastic Load Balancer (ELB). You must log all API calls that are made to the ELB. How can you accomplish this goal?

- 1. Use SQS to capture messages sent to the ELB
- 2. Enable CloudTrail to log API calls to the ELB(Correct)
- 3. Use SNS to push the logs to an S3 bucket
- 4. Enable Cloud Formation to log API calls to the ELB

*Correct Answer(s):*
 2. Enable CloudTrail to log API calls to the ELB

**Explanation:**
AWS CloudTrail can be used to monitor API within your AWS account. You can analyze log files to view past activity. Logs for API calls include the identity of the API caller, the time, and the source IP address. It also shows the request parameters, and the response returned by the AWS service.  https://aws.amazon.com/cloudtrail/faqs/

## Question 72:

 You have a running instance equipped with multiple Elastic Network Interfaces (ENI). You want to detach some of these ENIs and attach them to another instance. Which statements regarding this task are correct? (Choose two.)

- 1. Interfaces cannot be detached from one instance and attached to another.
- 2. You cannot detach the primary (eth0) instance from an instance, even if the instance is stopped(Correct)
- 3. You can detach secondary interfaces from a running instance(Correct)
- 4. The primary interface (eth0) can only be detached from an instance that is stopped.

*Correct Answer(s):*
 2. You cannot detach the primary (eth0) instance from an instance, even if the instance is stopped3. You can detach secondary interfaces from a running instance

**Explanation:**
You can detach and attach secondary network interfaces to and from instances. You cannot detach the primary (eth0) interface. This can be performed even when an instance is running (hot attach). You can also attach an interface to an instance that is stopped (warm attach), or when the instance is being launched (cold attach).  https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/using-eni.html

## Question 73:

 Can you enable encryption on an EBS volume that has already been created?

- 1. No(Correct)
- 2. Yes

*Correct Answer(s):*
 1. No

**Explanation:**
Encryption cannot be activated on an existing EBS volume. If this data needs to be encrypted you should create a new EBS volume and move the data from the old volume using a tool like Rsyinc. For more details, see: https://tinyurl.com/y9mseu88

## Question 74:

 What are the primary benefits of a reserved instance? (Choose two.)

- 1. To create instances on dedicated physical hardware.
- 2. To have reserved compute capacity.(Correct)
- 3. To enforce standardization to a specific AMI.
- 4. To reduce total cost of ownership.(Correct)

*Correct Answer(s):*
 2. To have reserved compute capacity.4. To reduce total cost of ownership.

**Explanation:**
Reserved Instances give you the opportunity to save money by making an investment in computing capacity on AWS. When used correctly they can provide huge savings, but they also come with some potential risk. A reserved instance allows you to purchase a reservation of capacity for either one or three years. Because you are committing to purchase the compute capacity for a longer term, the price is greatly reduced. Reserved instances are supported on EC2 and RDS, as well as CloudFront. When you purchase a Reserved Instance you can opt for no upfront payment, partial upfront, or all upfront. The more you pay upfront, the lower the rate. If an Availability Zone is specified, EC2 reserves capacity matching the attributes of the RI.   https://aws.amazon.com/ec2/pricing/reserved-instances/

## Question 75:

 Your organization has a group of EC2 instances that are of critical importance. You want to ensure that these instances can only be terminated by specific employees. Which option will accomplish this goal?

- 1. Configure MFA
- 2. Configure EC2 termination protection
- 3. Configure Resource-based tagging(Correct)
- 4. Create a role that prevents the termination of critical instances

*Correct Answer(s):*
 3. Configure Resource-based tagging

**Explanation:**
Tags can be used to organize AWS resources. This is helpful when you have similar resources that you need to categorize. For example, you may have a group of EC2 instances that belong to the development team, and other instances that belong to the production team. You could tag those instances to keep them organized, and to assign roles appropriately. Tags can only be assigned to an object that already exists. Termination Protection will not help because it is enforced at the instance level for all users. Termination Protection can prevent the accidental termination of an EC2 instance. It can be enabled from the AWS console, command line interface, or API. Termination Protection is disabled by default. You can enable Termination Protection on an instance at any time. Multi-Factor Authentication (MFA) would not help in this scenario. MFA is a good way to control access to AWS, but once the user is authenticated the job of MFA is done, and it will not prevent them from carrying out specific actions.   https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/Using_Tags.html

## Question 76:

 You would like to allow users to log into a mobile application using Facebook credentials, and automatically give them access to write to an S3 bucket. Which service can be used to accomplish this?

- 1. Web Identity Federation(Correct)
- 2. Mobile Application Identity Federation
- 3. Mobile Identity Service
- 4. Web Application Firewall

*Correct Answer(s):*
 1. Web Identity Federation

**Explanation:**
Custom developed Apps may have the need to access resources on AWS. Any requests to AWS services must be signed with an AWS access key. The access key is sensitive information, and should not be distributed to App users. Rather than distributing the access key you can configure apps to request temporary AWS security credentials as needed web identity federation. Web identity federation allows users to sign in using a well-known identity provider (IdP) like Login with Amazon, Facebook, Google. Once signed in they will receive an authentication token (OAuth or OpenID Connect) and be granted temporary security credentials in AWS.  These credentials are associated with a role that restricts the AWS functions that can be performed.

## Question 77:

 Which statements regarding a Network Load Balancer are correct? (Choose two.)

- 1. Network ELB supports load balancing to resources located in the customer datacenter(Correct)
- 2. Instances can be placed in multiple AZs behind a Network ELB(Correct)
- 3. Network ELB cannot load balance to multiple ports on the same instance
- 4. A CNAME record can be used to resolve a zone apex to a Network ELB

*Correct Answer(s):*
 1. Network ELB supports load balancing to resources located in the customer datacenter2. Instances can be placed in multiple AZs behind a Network ELB

**Explanation:**
Elastic Load Balancing supports Application Load Balancers, Network Load Balancers, and Classic Load Balancers. Network Load Balancers operate at Layer 4. The Network ELB routes connections to targets including EC2 instances, containers and IP addresses. It is integrated with Auto Scaling, Amazon EC2 Container Service (ECS), and Amazon CloudFormation.   https://aws.amazon.com/elasticloadbalancing/details/

## Question 78:

 You have created multiple subnets in a VPC. Some are public, some are private. Instances in both subnets are all connected to the default security group. Should you be able to route across these subnets by default?

- 1. Yes, each VPC automatically has an entry in the route table for the local network(Correct)
- 2. Yes, but only if the networks are manually opened in the security group
- 3. No, it is not possible to route between subnets without creating a L2 VPN
- 4. Yes, but only if a route is manually created in the routing table

*Correct Answer(s):*
 1. Yes, each VPC automatically has an entry in the route table for the local network

**Explanation:**
All instances associated with the default security group can communicate, unless explicitly blocked by a user created rule. A local route is automatically created for the CIDR range of the VPC so that traffic can route between subnets. You can use security groups to create a virtual firewall that can be applied across multiple instances. Rules are configured to control inbound and outbound traffic.    https://docs.aws.amazon.com/AmazonVPC/latest/UserGuide/VPC_SecurityGroups.html#DefaultSecurityGroup

## Question 79:

 Which statements regarding EBS volumes are correct? (Choose two.)

- 1. An EC2 instance store should be used for the operating system of the instance.
- 2. EBS volumes are global resources that can be accessed in multiple regions.
- 3. Snapshots are a good way to copy a volume to a different Availability Zone.(Correct)
- 4. An EBS volume is local to an Availability Zone (AZ).(Correct)

*Correct Answer(s):*
 3. Snapshots are a good way to copy a volume to a different Availability Zone.4. An EBS volume is local to an Availability Zone (AZ).

**Explanation:**
An EBS volume is local to an Availability Zone (AZ). The volume is replicated across hardware within the AZ to prevent data loss due to failure of any single hardware component. A volume can be attached to any EC2 instance within that AZ. Once it is attached the instance can interact with it as if it were a local drive, and format it with the appropriate file system. You can take snapshots of an EBS volume. The snapshot is a point-in-time picture of the volume that is stored in S3. Like all data stored on S3, it will exist redundantly in multiple Availability Zones. Snapshots can be used to create multiple new EBS volumes. This is useful if you need to move a volume to a different AZ. You can create a new volume based on the snapshot, and it will be an exact copy of the original. https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/EBSVolumes.html

## Question 80:

 You need to store many large video files as objects in S3. Which services could be used to expedite the upload process? (Choose two.)

- 1. MultiPart Upload(Correct)
- 2. Auto-scaling Write Capacity Units
- 3. Provisioned IOPs
- 4. Transfer Acceleration(Correct)

*Correct Answer(s):*
 1. MultiPart Upload4. Transfer Acceleration

**Explanation:**
Amazon S3 Transfer Acceleration provides fast, secure transfers of files to S3 buckets. Transfer Acceleration leverages CloudFront edge locations. You transfer the data to a nearby edge location, and AWS routes the data to S3 over an optimized network path. Multipart upload breaks up a large object into a set of parts. If transmission of a part fails you can retransmit that individual part without affecting the other parts. Multipart upload is recommeded for objects over 100 MB.   https://docs.aws.amazon.com/AmazonS3/latest/dev/transfer-acceleration.html

## Question 81:

 What happens if the the spot price exceeds your bid price and you have running spot instances?

- 1. Your instances will be shut down, but not terminated. If you spot price drops below your bid the instances will boot back up.
- 2. Your instances will continue to run until their task is complete at the higher price.
- 3. You must terminate your instances either manually or by using CloudWatch.
- 4. Your instances will be terminated after a 2 minute warning.(Correct)

*Correct Answer(s):*
 4. Your instances will be terminated after a 2 minute warning.

**Explanation:**
Spot instances only run if your bid price exceeds the Spot price. The bid price is the maximum hourly price you are willing to pay for an instance type. If the price of the spot instance becomes higher than the bid price, the instance will be shut down. They offer all the same performance and reliability characteristics of any other EC2 instance, but can reduce your operating costs by up to 50-90%. They are useful for applications such as stateless web services, image rendering, big data analytics and massively parallel computations because of their temporary nature, and the high scalability.

## Question 82:

 You need to create a Petabyte-scale data warehouse that supports ODBC and JDBC connections. Which AWS service should you use?

- 1. Redshift(Correct)
- 2. Aurora
- 3. RDS
- 4. DynamoDB

*Correct Answer(s):*
 1. Redshift

**Explanation:**
Redshift is Amazon’s data warehousing solution. It provides a fast, fully managed data warehouse that can be used to analyze all your data using your existing business intelligence tools. Management, monitoring, and scaling tasks are all automated, making management of your data warehouse much simpler. Redshift supports JDBC and ODBC connections, which allow you to use SQL clients to access the required data.

## Question 83:

 How can you integrate AWS IAM with a locally hosted LDAP identity source?

- 1. Configure SAML to pass a token from your identity source to AWS.(Correct)
- 2. Use the LDAP migration wizard
- 3. Create an IAM policy that queries LDAP
- 4. Import IAM roles into your on-premise servers

*Correct Answer(s):*
 1. Configure SAML to pass a token from your identity source to AWS.

**Explanation:**
You can create a SAML 2.0 identity provider (IdP) that will allow you to integrate an on-site solution with AWS to provide Single Sign-On (SSO). Examples of supported IDP solutions include Shibboleth and Active Directory Federation Services. For example, a user will sign in to an on-premise solution, such as Active Directory. Because a trust exists between Active Directory and AWS, that user does not need to sign into AWS to gain access to AWS resources. This user is referred to as a federated user. Once the IdP is created in AWS you must create one or more IAM roles. The job of this particular role is to allow your IDP to request temporary security credentials from AWS for federated users. The federated users will be able to carry out functions in AWS based on the policies assigned to the role.   https://docs.aws.amazon.com/IAM/latest/UserGuide/id_roles_common-scenarios_federated-users.html

## Question 84:

 You want to use separate AWS accounts for two different teams (Team1 and Team2), but want to have a single bill under a master account. Administrators with access to the master account should be able to stop or terminate resources in the other accounts. Which option will accomplish this goal?

- 1. Create IAM users in the Master account with full Admin permissions. Create cross- account access roles in the Team1 and Team2 accounts. Inherit permissions from the Master account.
- 2. Create IAM users in the Master account. Create cross-account access roles in the Team1 and Team2 accounts. Grant these roles full Admin permissions, and give the Master account access to these roles.(Correct)
- 3. Create IAM users in the Team1 and Team2 accounts. Create cross-account access roles in the Master account. Grant full Admin permissions to the Team1 and Team2 accounts.
- 4. Create IAM users in the Team1 and Team2 account. Create cross-account access roles in the Team1 and Team2 account. Grant full Admin permissions to the Team1 and Team2 accounts.

*Correct Answer(s):*
 2. Create IAM users in the Master account. Create cross-account access roles in the Team1 and Team2 accounts. Grant these roles full Admin permissions, and give the Master account access to these roles.

**Explanation:**
You should create IAM users in the Master account. These are the user accounts that the administrators will sign in with. Create cross-account access roles in the Team1 and Team2 accounts. This will allow administrators from other accounts to perform the actions specified in these roles. Grant these roles full Admin permissions, and give the Master account Access to these roles. As you are creating the role you will have the option to allow IAM users from a 3rd party AWS account to access this account. You can then specify an external ID to grant access to.  https://docs.aws.amazon.com/IAM/latest/UserGuide/tutorial_cross-account-with-roles.html

## Question 85:

 You are a developer with limited knowledge of AWS Architecture. Which tool should you use to automatically create a load balanced, auto scaling AWS environment for your application?

- 1. Elastic Beanstalk(Correct)
- 2. EBS
- 3. Cloud Formation
- 4. Elastic Transcoder

*Correct Answer(s):*
 1. Elastic Beanstalk

**Explanation:**
AWS Elastic Beanstalk can be used to deploy web applications and services developed with Java, .NET, PHP, Node.js, Python, Ruby, Go, and Docker on familiar servers such as Apache, Nginx, Passenger, and IIS. It is designed for developers to upload their code, which is then inspected by Amazon. Amazon then provisions the required resources for you, including capacity provisioning, load balancing, auto-scaling, and application health monitoring. You can access the underlying resources at any time and maintain full administrative control. There is no additional charge for Elastic Beanstalk as a feature itself, but you must pay for AWS resources needed run your applications and the storage that is consumed.  https://aws.amazon.com/elasticbeanstalk/

## Question 86:

 Which of the following statements about block storage is correct?

- 1. Data is managed at the file level
- 2. S3 and EFS are block storage solutions
- 3. Data is managed at the object level
- 4. Data is managed by sequences of bytes or bits(Correct)

*Correct Answer(s):*
 4. Data is managed by sequences of bytes or bits

**Explanation:**
Block storage devices manage data in sequences of bytes or bits. These are referred to as blocks. Traditional hard disks are the best know example of a block storage device. EC2 supports two types of block devices: Instance Store and EBS. An EC2 instance store is temporary storage on disks that are physically attached to the host computer. There are many use cases for this storage type, such as temporary content or data that is replicated across many instances. The data is discarded when the associated EC2 instance stops or is terminated. This storage is not meant for valuable, long-term data. You can back this data up periodically to S3 or EBS. SSD instance stores can be used when you need high performance and low latency, but do not need data to persist when the instance is terminated. Elastic Block Storage provides virtual “Disks” for your EC2 instances. Think of EBS as raw, unformatted disks. They are formatted with a file system, such as NTFS or ESXt, by the instance. Multiple EBS devices can be supported on the same EC2 instance, just like multiple disks on a VM.

## Question 87:

 Which statements regarding SQS are correct? (Choose two.)

- 1. SQS guarantees that messages will not be delivered twice.
- 2. SQS provides FIFO delivery of messages.
- 3. SQS does not provide push notification of new messages.(Correct)
- 4. SQS guarantees that all messages will be delivered at least once.(Correct)

*Correct Answer(s):*
 3. SQS does not provide push notification of new messages.4. SQS guarantees that all messages will be delivered at least once.

**Explanation:**
Simple Queue Service (SQS) is the first service ever launched on AWS. SQS is a fully managed message queuing service. The job of SQS is to store messages as they travel between applications. This makes it simple to decouple and distribute components of a cloud application. With SQS, you don’t need to manage a highly available messaging cluster of your own. And as with most AWS solutions, you only pay for what you use.

## Question 88:

 Which AWS feature can be used to place instances on different hardware within a single Availability Zone?

- 1. EC2 Auto Recovery
- 2. Autoscaling Group
- 3. Cluster Placement Group(Correct)
- 4. Elastic Load Balancer

*Correct Answer(s):*
 3. Cluster Placement Group

**Explanation:**
A cluster placement group can be used to place instances on different hardware within an Availability Zone (AZ). This is ideal for applications that require low network latency communcation, such as clustered applications. This does not provide protection from an AZ failure, but ensures some level of availability by placing the instances on different hosts within the AZ.    https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/placement-groups.html

## Question 89:

 You need to mount an NFS 4.1 share to an EC2 instance. Which AWS service can provide storage capacity compatible with NFS 4.1?

- 1. EFS(Correct)
- 2. Glacier
- 3. S3
- 4. EBS

*Correct Answer(s):*
 1. EFS

**Explanation:**
Amazon Elastic File System (Amazon EFS) is like a NAS device in the cloud. You can mount EFS to Amazon EC2 instances using NFS 4.1. This is a commonly used standard that allows the operating system to mount EFS storage directly. Multiple EC2 instances can access the same EFS file system, allowing you to share storage across multiple virtual servers. This can even work on VMs that are in different availability zones. You can also mount your Amazon EFS file systems to your own physical datacenter servers using AWS Direct Connect.    https://docs.aws.amazon.com/efs/latest/ug/mounting-fs.html

## Question 90:

 You are unable to open an SFTP connection to a web server that is running on an EC2 instance. What should you check?

- 1. Make sure port 22 is open in the security group.(Correct)
- 2. Check the DB Security Policy.
- 3. Make sure the IAM policy permits HTTP.
- 4. Update the guest operating system.

*Correct Answer(s):*
 1. Make sure port 22 is open in the security group.

**Explanation:**
For the exam you need to know the common port numbers (22 for SSH / SFTP, 443 for HTTP, etc). You should validate that port 22 is open on the security group. When you create a security group all inbound traffic is blocked because it has no inbound rules. The security group includes an implicit "deny all", meaning that any traffic not explicitly allowed is blocked. The security group includes a default outbound rule that allows all traffic. This rule can be removed, and you can specify certain types of traffic that should be allowed out. All instances associated with a security group can communicate, unless explicitly blocked by a user created rule.

## Question 91:

 Which statements regarding S3 Standard vs. S3 Infrequent Access (IA) are correct? (Chose two.)7

- 1. S3 IA charges a per-GB retrieval fee for data.(Correct)
- 2. S3 Infrequent Access provides the same level of availability as S3 Standard
- 3. S3 Standard provides lower latency.
- 4. Both tiers provide similar latency performance.(Correct)

*Correct Answer(s):*
 1. S3 IA charges a per-GB retrieval fee for data.4. Both tiers provide similar latency performance.

**Explanation:**
S3 Standard - Infrequent Access (S3 - IA) is ideal for data that is not needed very often. It is less costly per GB than S3 Standard, but still provides the same performance when you need to access data. A per GB retrieval fee is charged when data is accessed. Use S3-IA for long-term storage, backups, and as a data store for disaster recovery. You can have objects in the same bucket configured for either S3 Standard or S3 Infrequent Access. You can also configure a lifecycle policy to move data to a different storage class after a certain amount of time.

## Question 92:

 You have an on-premise storage array that you would like to use to cache key data locally. The data would be persistently stored in your AWS account. Which service can you use to accomplish this?

- 1. Elastic Block Store
- 2. S3 and CloudFront
- 3. Elastic File Share
- 4. Storage Gateway(Correct)

*Correct Answer(s):*
 4. Storage Gateway

**Explanation:**
You have an on-premise storage array that you would like to use to cache key data locally. The data would be persistently stored in your AWS account.

## Question 93:

 You need to analyze a large amount of data stored on S3. You are using the c3 instance type. You need to reduce the time it takes the analysis to complete. CPU utilization is presently low. What option would reduce the time required in a cost-effective manner?

- 1. Add more c3 instances.
- 2. Break up the files on Amazon S3 into smaller sizes.
- 3. Migrate the data that must be analyzed to Glacier.
- 4. Use instances that can handle more storage I/O.(Correct)

*Correct Answer(s):*
 4. Use instances that can handle more storage I/O.

**Explanation:**
In this scenario CPU usage is low, and we are using compute optimized instances (c3) to perform the data analysis. By using a different instance type (such as I2) we can optimize the storage performance, and reduce the time required to analyze the data.

## Question 94:

 What is an EC2 Compute Unit (ECU)?

- 1. A thread of execution
- 2. An EC2 instance
- 3. A unit of CPU Capacity(Correct)
- 4. A CPU core attached to an instance

*Correct Answer(s):*
 3. A unit of CPU Capacity

**Explanation:**
An EC2 compute unit is a unit of measurement that AWS uses to quantify CPU resources. With AWS you do not purchase or lease a particular physical processor. Your workloads may run on different processors from different manufacturers at any given time. There may be several different types of physical hardware underlying EC2 instances, but the user experience is consistent, regardless. Measuring compute capacity in ECUs makes it easy to compare and contrast CPU capacity across different instance types. For the exam be sure to memorize acronyms like ECU, and what they stand for.  https://www.botmetric.com/blog/aws-ec2-instance-type-pricing-ecu-vs-vcpu/

## Question 95:

 Which statements regarding Direct Connect are accurate? (Choose two.)

- 1. You cannot extend a local VLAN into Direct Connect.(Correct)
- 2. Direct Connect provides a private dedicated connection to a VPC.(Correct)
- 3. Direct Connect does not support BGP.
- 4. You cannot configure a VLAN Trunk over AWS Direct Connect.

*Correct Answer(s):*
 1. You cannot extend a local VLAN into Direct Connect.2. Direct Connect provides a private dedicated connection to a VPC.

**Explanation:**
Direct Connect can be used to create a dedicated network connection between your organization and an AWS VPC. This is useful if you need a high-throughput, consistent network experience. All data transferred over this connection is charged a reduced Direct Connect data transfer rate. 1 Gbps and 10 Gbps connections are available, and multiple connections can be supported for increased bandwidth. Multiple VLANs can be carried over the connection using an 802.1q trunk port. For example, assume you have private resources on AWS. You can access them over a defined VLAN that is dedicated to private traffic. Other VLANs could be used to access resources with public IP addresses. For routing purposes, Direct Connect requires the use of the Border Gateway Protocol (BGP) with an Autonomous System Number (ASN) and IP Prefixes. This allows your routers to send the appropriate traffic to AWS, and general traffic can flow out of an existing connection. Numerous partners can provide these connections. For a full list see: aws.amazon.com/directconnect/partners/   Direct Connect FAQs: https://aws.amazon.com/directconnect/faqs/

## Question 96:

 What consistency model is provided for data written to S3? (Choose two.)

- 1. Eventual consistency for PUTS
- 2. Eventual consistency for overwrite PUTS and DELETES(Correct)
- 3. Read-after-write consistency for PUTS of new objects(Correct)
- 4. Immediate consistency for PUTS and DELETES

*Correct Answer(s):*
 2. Eventual consistency for overwrite PUTS and DELETES3. Read-after-write consistency for PUTS of new objects

**Explanation:**
S3 offers read after write consistency for PUTS to new objects, and eventual consistency for PUTS and DELETES of existing objects. This means that when you upload an object to s3 it is immediately available to be read. However this object also needs to be replicated to multiple devices across multiple physical facilities, so if you decide to modify or delete an object it may take time for those changes to take effect universally. If you make a change and immediately try to read the changed file, it may not reflect the changes you just made.   https://aws.amazon.com/s3/faqs/

## Question 97:

 What does it mean to terminate an EC2 instance?

- 1. The instance is destroyed but data on Instance Store is still available.
- 2. The instance is destroyed and any data on Instance Store is deleted.(Correct)
- 3. The instance is shut down, and any data on Instance Store is deleted.
- 4. The instance is suspended and all processes are terminated until it is resumed.

*Correct Answer(s):*
 2. The instance is destroyed and any data on Instance Store is deleted.

**Explanation:**
You should terminate an instance only when it is no longer needed. Once an instance is terminated it cannot be restarted. The instance will be visible in the console for a brief period and will then be deleted. If you have created an EC2 Instance Store any data on it will be deleted. EBS root volumes will also be deleted. Other volumes may persist, depending on how you have configured the delete on termination attribute.

## Question 98:

 How does EC2 Auto Recovery improve uptime for applications hosted on EC2 instances?

- 1. If an instance fails all traffic will be re-directed to a secondary instance.
- 2. If an instance has an operating system failure it will automatically reboot.
- 3. If a region-wide failure occurs the instance will restart in a different region
- 4. If an instance is running on a host that fails, the instance will automatically reboot on a different host.(Correct)

*Correct Answer(s):*
 4. If an instance is running on a host that fails, the instance will automatically reboot on a different host.

**Explanation:**
Auto Recovery can return your instance to service by rebooting it on another host. System Status checks monitor for a host failure. A loss of connectivity, power, or other similar problems will cause the instance to reboot on a different physical system.

## Question 99:

 What modes can an ELB be configured to run in? (Choose three.)

- 1. Application Load Balancer(Correct)
- 2. RDS Load Balancer
- 3. Classic Load Balancer(Correct)
- 4. Cross-Region Load Balancer
- 5. Network Load Balancer(Correct)

*Correct Answer(s):*
 1. Application Load Balancer3. Classic Load Balancer5. Network Load Balancer

**Explanation:**
ELB can operate in Network Load Balancer, Classic Load Balancer or Application Load Balancer modes. When you enable an Availability Zone (AZ) for the load balancer an ELB node is created in that AZ. Multiple AZs are recommended when using the Classic Load Balancer. It is required for the Application Load Balancer. Cross-zone load balancing distributes traffic evenly across all registered instances in all enabled AZs. A Network Load balancer operates at Layer 4 of the OSI model, and can be used to distribute traffic across different types of targets.   https://aws.amazon.com/elasticloadbalancing/

## Question 100:

 You have just created an RDS instance in a VPC, and must control which IP addresses or EC2 instances have access to your DB Instance. Your configuration must affect only the specified RDS instances, and not the entire subnet. What should you configure?

- 1. EC2 Security Group
- 2. Network Access List
- 3. VPC Security Group(Correct)
- 4. DB Security Group

*Correct Answer(s):*
 3. VPC Security Group

**Explanation:**
A VPC security group is used to control which IP addresses and EC2 instances can access RDS DB instances inside a VPC. A DB security group is only used for RDS instances that are not within a VPC. A Network ACL is created and applied to the entire subnet.   https://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/Overview.RDSSecurityGroups.html

