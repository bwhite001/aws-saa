# Practice Test AWS Solutions Architect Associate SAA C03Practice Test AWS Solutions Architect Associate SAA C03: 


## Question 1:

 A sports streaming service needs to handle millions of viewers during popular events. What infrastructure provisioning strategy can optimize the cost while meeting the performance needs?

- 1. Provision spot instances to handle the peak traffic and leave them running all the time
- 2. Purchase sufficient reserved instances to handle the baseline traffic and launch additional on-demand instances based on traffic
- 3. Purchase sufficient reserved instances to handle the baseline traffic and launch additional spot instances based on traffic(Correct)
- 4. Purchase sufficient reserved instances to handle the peak traffic and leave them running all the time

*Correct Answer(s):*
 3. Purchase sufficient reserved instances to handle the baseline traffic and launch additional spot instances based on traffic

**Explanation:**
You can blend reserved instances and spot instances. You can use a few reserved instances to cover baseline traffic and add spot instances to cover the traffic increase during popular events. You can gradually terminate the spot instances when the traffic drops after the event. Instead of spot, you can use the on-demand instances at a much higher cost.Knowing what purchasing option to use is an important architectural decision - Spot, Savings Plan, Reserved Instances, On-demandPlease watch my YouTube hands-on tutorial on this topicAWS Pricing Calculation Tutorial - Spot, Savings Plan, Reserved Instances, On-demand - YouTube (30 minutes)https://www.youtube.com/watch?v=sb266536q_k

## Question 2:

 You would like to automatically replace instances that are not healthy due to underlying infrastructure or common guest OS related issues.  In order to do so with AutoScaling, you need to:

- 1. Subscribe to CloudWatch Events from Autoscaling to track the instance status changes
- 2. Configure auto scaling to perform instance and system status check
- 3. Autoscaling automatically does this for you(Correct)
- 4. Setup alarm to monitor system and instance status checks and hook it to up to AutoScaling action

*Correct Answer(s):*
 3. Autoscaling automatically does this for you



## Question 3:

 The Recovery Point Objective (RPO) is set to two hours for your on-premises systems. What does this mean?(Choose Two)

- 1. It indicates an acceptable amount of data loss measured in time(Correct)
- 2. You can restore your systems to a state where data looks identical to how it was 2 hours before the disaster struck(Correct)
- 3. It will take at least 2 hours to restore your system after a disaster strikes
- 4. It will take a maximum of 2 hours to restore your system after a disaster strikes

*Correct Answer(s):*
 1. It indicates an acceptable amount of data loss measured in time2. You can restore your systems to a state where data looks identical to how it was 2 hours before the disaster struck

**Explanation:**
Recovery Point Objective indicates acceptable amount of data loss measured in time. If disaster strikes at time T, if RPO is 2 hours, then you have process and procedures in place to restore the systems as it appeared at T-2.

## Question 4:

 EC2 instance has a Security group with following rules: Inbound rule allows HTTP request on port 80 from 0.0.0.0/0.  Outbound rule allows all traffic to destination 10.0.0.0/16. If this instance receives a HTTP request from IP address 99.34.45.210, what is the behavior observed?

- 1. Inbound request is blocked
- 2. Instance can receive the request and respond back(Correct)
- 3. Instance can receive the request, but response is blocked
- 4. Outbound request is allowed to anywhere

*Correct Answer(s):*
 2. Instance can receive the request and respond back

**Explanation:**
Security Groups are stateful.  If a security group allows an outbound request from your instance, corresponding response is also allowed. Similarly, if security group allows a particular inbound request, corresponding response is also allowed.

## Question 5:

 An application running on EC2 instances stores all critical, error, warning and informational messages to log files in the instance.  Your support team would like to monitor the error trend and keep this log data for a minimum of 90 days, even when instances are terminated.  Which one of these options would you recommend?

- 1. CloudWatch Events
- 2. Custom Scripts to publish log metrics to CloudWatch and store log files in S3
- 3. CloudWatch Logs(Correct)
- 4. S3

*Correct Answer(s):*
 3. CloudWatch Logs

**Explanation:**
With CloudWatch Logs, we can gather log files to a central location, analyze and publish metrics based on log content, and store the logs for the desired retention period.

## Question 6:

 Your lambda function needs to access internet and other AWS Service end points. What steps are needed to enable internet access?

- 1. Attach Lambda to a public subnet in your VPC
- 2. Ensure Lambda Security Group allows outbound internet access
- 3. By default, Lambda can access internet(Correct)
- 4. Add a NAT device to route traffic to internet services

*Correct Answer(s):*
 3. By default, Lambda can access internet

**Explanation:**
By default, Lambda allows outbound calls to internet

## Question 7:

 Your application is generating several false alarms. The alarm is currently based on the CPU utilization metric. Upon investigation, you found that the false alarms can be reduced if you consider the pending items in the SQS Queue. How would you ensure the alarm goes into ALARM state only when both the CPU utilization and SQS Queue length metrics breach the threshold?

- 1. Set up CloudWatch Logs to analyze CPU and SQS Pending Queue data. Use a metric filter to generate a new composite metric
- 2. Configure multi-metrics alarm in CloudWatch
- 3. Configure CloudWatch Synthetic Canaries to monitor multiple metrics
- 4. Configure Composite Alarm that is based on both CPU Utilization alarm and SQS Queue Length Alarm(Correct)

*Correct Answer(s):*
 4. Configure Composite Alarm that is based on both CPU Utilization alarm and SQS Queue Length Alarm

**Explanation:**
With CloudWatch, you can create two types of alarms: metric and composite. A metric alarm watches a single metric, and when the metric breaches the threshold, the alarm changes to an "ALARM" state. A composite alarm is a new capability that considers the state of multiple alarms. The outcome of a composite alarm depends on the rule expression you define. For example, let's say you have a metric alarm to monitor CPU utilization and another to monitor SQS Queue Length. You can create a composite alarm when you need to perform a certain action only when both CPU and SQS Queue Length alarms are in the ALARM state. Rule expression allows you to combine these underlying metric alarms or other composite alarms and create a new Alarm based on the state of these existing alarms. AWS recommends composite alarms to reduce alarm noise. With CloudWatch Synthetics, you can create the Canaries, a configurable script that runs on a schedule to monitor your endpoint and APIs. Using the Canaries, you can continuously monitor the health of your application even when you don't have any customer traffic. Canaries are written using Node.js or Python and also give you programmatic access to a headless chrome browser (headless refers to a lack of GUI or user interface. You can use this capability for automated tests)

## Question 8:

 When distributing Private Content with CloudFront, how do you make sure users do not bypass security measures and go directly to custom origin servers and S3 location?  (Choose Two)

- 1. Configure CloudFront to forward custom headers to your publicly accessible origin server.  Verify Custom header and value in your application(Correct)
- 2. Deploy Custom Origin Server in private subnets
- 3. Lockdown S3 with CloudFront Origin Access Identity (OAI) and remove permissions for others(Correct)
- 4. Deploy CloudFront to private subnet in your VPC

*Correct Answer(s):*
 1. Configure CloudFront to forward custom headers to your publicly accessible origin server.  Verify Custom header and value in your application3. Lockdown S3 with CloudFront Origin Access Identity (OAI) and remove permissions for others

**Explanation:**
CloudFront Origin needs to have a public endpoint. To prevent others from calling your Origin endpoints directly, you need to configure the endpoint to verify if the request is coming from CloudFront.A common pattern is configuring CloudFront to embed a specific header and value (either static value or dynamic values using Lambda@edge). You can verify the header content in your origin server to allow or deny access.You can configure CloudFront to embed specific code to a custom header and cross-check the header value in Origin Server.For S3, CloudFront uses Origin Access Identity (OAI) to access your S3 bucket. In the S3 bucket policy, you need to limit access only to this identity

## Question 9:

 A web application is configured with an internet facing Application Load Balancer (ALB).  There are several EC2 instances registered with the load balancer.  You need to collect details about the requester's IP address.  How can you find this information?

- 1. Use load balancer access Log Files(Correct)
- 2. Use web server Log Files
- 3. Application log Files
- 4. Use either load balancer access Logs or Web Server Logs

*Correct Answer(s):*
 1. Use load balancer access Log Files

**Explanation:**
The application load balancer sends requests to the web server on behalf of the client. So, your web server will contain only the load balancer IP address as the requester. To find the client's IP address, we need to look at the load balancer logsThe Network Load Balancer works differently and forwards the client IP address to your application; in this case, your web server would know the requester's IP address

## Question 10:

 Your team is using S3 to store large number of files. The access pattern is not clearly defined, and users can access any of the files. The data needs to be immediately accessible when needed. Based on storage analysis, you found that less than 1% of the data is read by users. Which storage class would you use to lower the overall storage costs while meeting the access requirements? (Choose Two)

- 1. S3 One Zone IA
- 2. S3 Glacier Instant Retrieval(Correct)
- 3. S3 Standard
- 4. S3 Infrequent Access(Correct)
- 5. S3 Glacier Deep Archive

*Correct Answer(s):*
 2. S3 Glacier Instant Retrieval4. S3 Infrequent Access

**Explanation:**
S3 Glacier Instant Retrieval storage class offers instant access to data while keeping the storage costs low. There is a separate retrieval cost when data is accessed. S3 Infrequent Access is also a possible option. Interestingly Glacier Instant Retrieval Storage charges are 1/3rd that of S3 Infrequent Access; whereas retrieval charges are 3 times greater than S3 Infrequent Access tier. Glacier Deep Archive offers lowest storage cost; however, data retrieval will take hours. S3 Standard is the most expensive option meant for frequently accessed data. With One Zone IA, there is a risk of data loss. Another possible and valid choice (if given) is the Intelligent-tiering storage that automatically transitions to appropriate storage tier based on access patterns.

## Question 11:

 My application uses CloudFront distribution to reach a global audience. The application uses HTTPS to accept payment information (credit card, debit card, bank information) for subscriptions. This payment information must be accessible only for specific billing components in the application and be protected from unauthorized access in other components.What should I do? (Choose Two)

- 1. Enable Field level encryption in CloudFront to protect sensitive data(Correct)
- 2. Enable Origin Access Identity
- 3. Enable TLS/SSL encryption from CloudFront to your Origin Load Balancer and then from Load Balancer to your Webservers(Correct)
- 4. Enable TLS/SSL encryption from CloudFront to your Origin Load Balancer
- 5. Route payment processing requests directly to Origin servers and bypass CloudFront

*Correct Answer(s):*
 1. Enable Field level encryption in CloudFront to protect sensitive data3. Enable TLS/SSL encryption from CloudFront to your Origin Load Balancer and then from Load Balancer to your Webservers

**Explanation:**
Since the application handles sensitive data, you must ensure SSL/TLS is turned on all the way to the web servers. If you terminate SSL at the load balancer, communication between the load balancer and the web server is unencrypted, leading to sensitive data access by components other than billing. CloudFront supports Field Level Encryption to protect sensitive data. With this capability, you can configure CloudFront to encrypt fields using the specified encryption keys. You would then configure the billing component to use the matching keys so that it can decrypt the sensitive data. Origin Access Identity (OAI) protects S3 buckets from unauthorized access. Bypassing CloudFront for payment processing is not required – CloudFront uses AWS's private network and keeps a live connection to your Origin. So, performance would be better even if the request needs to go to the Origin.https://docs.aws.amazon.com/AmazonCloudFront/latest/DeveloperGuide/field-level-encryption.htmlhttps://aws.amazon.com/blogs/networking-and-content-delivery/adding-http-security-headers-using-lambdaedge-and-amazon-cloudfront/

## Question 12:

 You have a pool of EC2 instances to manage application requests.  Application has a metric that tracks pending requests and you would like to configure Autoscaling to add or remove instances based on this application metric.  How can you accomplish this?

- 1. Autoscaling actions can be performed only using standards metrics and status checks published by AWS Services
- 2. Publish Application metrics to CloudWatch and use CloudWatch alarms to trigger autoscaling actions(Correct)
- 3. Use a Lambda function to update Autoscaling group desired count
- 4. Update Autoscaling group desired count from within the application

*Correct Answer(s):*
 2. Publish Application metrics to CloudWatch and use CloudWatch alarms to trigger autoscaling actions

**Explanation:**
CloudWatch supports custom metrics and application can take advantage of this capability to push relevant metrics to CloudWatch.  Once it is available in CloudWatch, you can use rest of the capabilities provided by CloudWatch to monitor based on that metric

## Question 13:

 Messages published by clients need to be stored in AWS for consumption by many applications. The message arrival order must be preserved. The processing time for each message would exceed 24 hours. Which service would you use for this requirement?

- 1. SQS FIFO Queue
- 2. SQS Standard Queue
- 3. Kinesis Data Streams(Correct)
- 4. EventBridge

*Correct Answer(s):*
 3. Kinesis Data Streams

**Explanation:**
Kinesis Data Streams can preserve the order of messages (arranged as a time order series of records) and make it available for multiple applications. If it helps, you can visualize Kinesis Data Streams as an in-memory database that maintains records as a time-ordered sequence. Multiple applications can read these records at the same time. SQS Standard Queue does not preserve the message arrival order. SQS FIFO maintains the arrival order; however, a message in SQS is delivered only to one consumer. (i.e., multiple consumers cannot read the same message). In addition, the maximum processing time of a message in SQS is 12 hours.

## Question 14:

 A newly created IAM user has:

- 1. Default read only access
- 2. Default allow to all resources
- 3. Explicity deny to all resources
- 4. Default deny to all resources(Correct)

*Correct Answer(s):*
 4. Default deny to all resources

**Explanation:**
Permissions have to be explicitly granted; otherwise, they fall into default deny

## Question 15:

 You are using Simple Queue Service to hold messages and the consumer application processes the messages on a best effort basis.   How long can the message stay in the queue if the consumer application is down for extended periods?

- 1. 14 days (Correct)
- 2. 24 hours
- 3. 7 days
- 4. User Configurable

*Correct Answer(s):*
 1. 14 days 

**Explanation:**
Messages can be retained in SQS queues for up to 14 days.  Minimum is 1 minute

## Question 16:

 Your application receives traffic only during specific hours of the day. You are using AWS Lambda function for your backend logic.  What behavior can you observe with Lambda? (Choose Two)

- 1. For sparingly used systems, Lambda may not be ideal choice as there is a charge incurred whether you use the function or not
- 2. Lambda capability is instant-on and always available
- 3. Lambda may incur a startup delay if your functions are invoked after a long period of idle(Correct)
- 4. Lambda dynamically scales to handle concurrent requests(Correct)

*Correct Answer(s):*
 3. Lambda may incur a startup delay if your functions are invoked after a long period of idle4. Lambda dynamically scales to handle concurrent requests

**Explanation:**
By default, Lambda allows 1000 concurrent executions across all functions within a region. You can increase this limit by contacting support. Lambda also incurs a cold-start delay when a function is invoked after a long idle period. To prevent cold-start delay, you can optionally provision lambda capacity (called as Lambda provisioned concurrency) to keep them ready all the time (at an extra cost, of course)

## Question 17:

 You are noticing that the lambda function you wrote is working well functionally. However, the function execution time is taking longer than expected. What are the possible next steps to troubleshoot this issue? (Choose Two)

- 1. Increase Memory(Correct)
- 2. Enable X-Ray(Correct)
- 3. Increase vCPUs
- 4. Use Step functions
- 5. Disable Lambda Alias and directly call the Lambda function

*Correct Answer(s):*
 1. Increase Memory2. Enable X-Ray

**Explanation:**
Memory is the principal lever available to Lambda developers for controlling the performance of a function. You can configure the amount of memory allocated to a Lambda function, between 128 MB and 10,240 MB. The Lambda console defaults new functions to the smallest setting and many developers also choose 128 MB for their functions.However, 128 MB should usually only be used for the simplest of Lambda functions, such as those that transform and route events to other AWS services. If the function imports libraries or Lambda layers, or interacts with data loaded from S3 or EFS, it’s likely to be more performant with a higher memory allocation.The amount of memory also determines the amount of virtual CPU available to a function. Adding more memory proportionally increases the amount of CPU, increasing the overall computational power available. If a function is CPU-, network- or memory-bound, then changing the memory setting can dramatically improve its performance.By enabling X-ray tracing, you can identify the time taken for specific API calls and functions in your lambda code. This information can help you in addressing the performance issueLambda Alias is used for hiding version details from callers. It is a good feature and can help when creating new versions of a lambda function and allow consumers to call only the stable version of your function. This feature is not going to cause performance issues.https://docs.aws.amazon.com/lambda/latest/operatorguide/computing-power.html

## Question 18:

 A company is using S3 to store employee files.  Employees are requesting files and documents stored in S3 to be presented as a local network drive.   How can you do this?

- 1. Use AWS Storage Gateway deployed as a Tape Gateway
- 2. Use AWS Storage Gateway deployed as a Volume Gateway
- 3. Use AWS Storage Gateway deployed as a File Gateway(Correct)
- 4. Use AWS Datasync

*Correct Answer(s):*
 3. Use AWS Storage Gateway deployed as a File Gateway

**Explanation:**
In the File Gateway mode of the Storage Gateway, you can present an S3 bucket as a network file share to your on-premises systems. Any changes (addition, deletion, updates) that you make to the files are automatically replicated in the S3 bucket. Datasync is used for copying data from existing NFS/SMB fileshares to AWS Storage services. Whereas, Storage Gateway in the File Gateway configuration eliminates the need for a separate on-premises file share and all data is automatically backed up to the S3 bucket.

## Question 19:

 Simple Queue Service NumberOfEmptyReceives metric shows a consistently high value, and you notice in the billing statement that too many requests are made to the Queue.Which one of these options can help address this issue?

- 1. Configure the application to poll less frequently
- 2. Use Short Polling
- 3. Use Long Polling(Correct)
- 4. Use a smaller EC2 instance size

*Correct Answer(s):*
 3. Use Long Polling

**Explanation:**
When the queue is empty, consumers will keep polling the queue, and this would result in lots of empty responses and an increase in usage charges.The receive-message call supports a wait-time parameter. When wait-time is 0, it is called Short polling, and the call will return immediately (either with a message or an empty response).When wait time is greater than zero, it is called Long polling. Here, the call waits until a new message is available or when the wait time expires. The maximum wait time is 20 seconds.The use of long polling can reduce the number of calls, minimize empty responses, and eliminate false-empty responses

## Question 20:

 A web application is configured with an internet facing Elastic Load Balancer (ELB).   In order to handle the internet traffic, EC2 instances registered with the load balancer must have:

- 1. Either Public or Elastic IP Address
- 2. Elastic IP Address
- 3. Private IP Address(Correct)
- 4. Public IP Address

*Correct Answer(s):*
 3. Private IP Address

**Explanation:**
Elastic load balancers route requests to the instance using private IP address. It is a security best practice to keep the web servers in the private subnets.

## Question 21:

 You are enhancing a service appointment scheduling system for an automobile dealership. The upgraded system must give a choice to customers to receive appointment confirmation using multiple mechanisms such as SMS, email, voicemail, etc. In addition, customers can reply to SMS messages to confirm or cancel an appointment. Which AWS service would you use for this?

- 1. AWS Amplify
- 2. Amazon Pinpoint(Correct)
- 3. AWS AppSync
- 4. Amazon AppFlow

*Correct Answer(s):*
 2. Amazon Pinpoint

**Explanation:**
Pinpoint is a multichannel marketing communication service that can send messages through email, SMS, voicemail, or push notifications. It supports transactional messages such as one-time passwords, purchase confirmations, or shipping notifications. You can also receive SMS messages from customers. For example, in response to a doctor appointment reminder, the customer can reply and confirm the appointment. In addition, you can also use this service for bulk communication to broadcast messages. AppFlow is a no-code solution to automate data flow by securely integrating third-party applications and AWS services and securely transferring data from SaaS applications like Salesforce, SAP, Zendesk, Slack, and ServiceNow. Using AWS Amplify, you can build full-stack web and mobile apps. Using AppSync, we can accelerate application development with serverless GraphQL and Pub/Sub APIs

## Question 22:

 When designing a VPC, you need to account for address space that would be consumed by three of these choices. Which one of these will not use your VPC address space?

- 1. Elastic Load Balancer
- 2. EC2 instances
- 3. Number of concurrent Lambda invocations
- 4. EBS Volumes(Correct)

*Correct Answer(s):*
 4. EBS Volumes

**Explanation:**
EBS Volumes do not use address space. The elastic load balancer nodes are deployed in your VPC subnet and without sufficient address space, your load balancer may not scale to handle traffic.  Lambda functions when configured to access your VPC private resources will use up addresses in the assigned subnet. EC2 instances are assigned address from your subnet

## Question 23:

 Your application uses a CloudFront distribution with a Network Load Balancer Origin. Which services would offer comprehensive protection and block denial-of-service attacks? (Choose two)

- 1. Protect CloudFront using AWS WAF(Correct)
- 2. Protect Network Load Balancer using AWS WAF
- 3. Enable Advanced Shield on Network Load Balancer(Correct)
- 4. Enable GuardDuty
- 5. Enable AWS Inspector

*Correct Answer(s):*
 1. Protect CloudFront using AWS WAF3. Enable Advanced Shield on Network Load Balancer

**Explanation:**
Let's rule out what is not possible – GuardDuty is an intrusion detection system that can detect suspicious activities. We need additional workflow and steps to review and block activities flagged by GuardDuty. AWS Inspector identifies software vulnerabilities in your EC2 instances and container images. Inspector does not block attacks. WAF can block malicious layer 7 attacks (Application Layer attacks). WAF currently integrates with CloudFront distribution, Application Load Balancer, and API Gateway. WAF does not directly integrate with Network Load Balancer. So, a common strategy is to use CloudFront in front of NLB and protect CloudFront with WAF. Shield Advanced protects individual resources against Layer 3 and 4 attacks (like DDoS) and currently supports EC2 instances, Elastic IPs, Elastic Load Balancers, CloudFront, Route 53 hosted zones, and Global accelerators. Shield Advanced customers also get access to AWS DDoS Response Team.

## Question 24:

 Your corporate requirement calls for filtering and blocking suspicious network traffic in and out of your VPCs. Which product would you use?

- 1. Configure Network ACL and Security Group firewalls
- 2. Use VPC Traffic Mirroring for inline traffic inspection and filtering
- 3. Configure WAF to protect your VPCs
- 4. Use Network Firewall(Correct)

*Correct Answer(s):*
 4. Use Network Firewall

**Explanation:**
The Network Firewall is an Intrusion prevention system (IPS) that actively monitors and blocks suspicious traffic to and from all your VPCs. This is a Stateful Firewall. Using Firewall Manager, you can centrally manage and apply mandatory Network Firewall security policies across newly created accounts and VPCs. VPC Traffic Mirroring duplicates the traffic for offline inspection. So, it is not an intrusion prevention system. NACL and Security Group needs to be configured properly; however, they are based on rigid rules on what to allow and block. Since the requirement calls for blocking suspicious traffic, we need an intelligent system that looks for attack patterns and blocks the traffic.Refer to the SAA C03 - Services Summary article/lecture in this course

## Question 25:

 Which of these will impact applications when a single availability zone in a region goes down? (Choose Two)

- 1. S3 One Zone Infrequent Access(Correct)
- 2. DynamoDB
- 3. S3 Standard
- 4. EBS(Correct)
- 5. EFS

*Correct Answer(s):*
 1. S3 One Zone Infrequent Access4. EBS

**Explanation:**
EBS volume is stored and replicated in a single availability zone that the customer specifies. S3 One Zone Infrequent Access stores data in a single availability zone. S3 automatically chooses the availability zone. Clients using these features will be impacted due to an availability zone outage.EFS, other S3 storage classes, and DynamoDB replicate data across multiple availability zones in a region. Consumer applications can continue to use it even when a single AZ goes down.

## Question 26:

 Your customer is a small business that works with lot of images .  These images need to be backed up in a secure offsite location.  Images are accessed very often initially and then rarely accessed after few days.  However, when needed, it needs to be accessible as quickly as possible.  How can you use AWS Cloud Storage for this?

- 1. Use AWS Storage Gateway deployed as a Volume Gateway
- 2. Use AWS Storage Gateway deployed as a File Gateway(Correct)
- 3. Use Glacier Storage
- 4. Use AWS Storage Gateway deployed as a Tape Gateway

*Correct Answer(s):*
 2. Use AWS Storage Gateway deployed as a File Gateway

**Explanation:**
File Gateway configuration can locally cache frequently used data and for data that is not in cache, it can retrieve from AWS. It automatically and securely backsup file to S3.  Volume gateway is used as block storage and not suitable for this requirement.  Tape and Glacier options are suitable for requirement that do not need immediate access to data

## Question 27:

 Due to frequent changes in compute demand in your organization, you cannot commit to reserving whole EC2 instances. So, everyone is using on-demand purchasing in your organization. What option does AWS provide for long-term customers with changing compute requirements?

- 1. Use Fractional Reservation Plans
- 2. Use On-demand
- 3. Use Savings plan(Correct)
- 4. Use Spot instances

*Correct Answer(s):*
 3. Use Savings plan

**Explanation:**
With the Savings plan, you purchase fractional compute (for example, $0.52/hour of usage) and commit to long-term use. Cost Explorer can analyze your past on-demand compute usage and recommend a dollar amount for savings plan purchases. You can purchase additional savings plan by periodically reviewing the on-demand usage. This gives you better flexibility. In comparison, a reservation requires you to commit in terms of a number of EC2 instances.Knowing what purchasing option to use is an important architectural decision - Spot, Savings Plan, Reserved Instances, On-demandPlease watch my YouTube hands-on tutorial on this topicAWS Pricing Calculation Tutorial - Spot, Savings Plan, Reserved Instances, On-demand - YouTube (30 minutes)https://www.youtube.com/watch?v=sb266536q_k

## Question 28:

 Your environment has several existing clients that use SFTP, FTP, FTPS, and AS2 protocols for file transfer. Which service offers a fully managed solution to move data into and out of AWS Storage services using these protocols?

- 1. Snowball Edge Compute Optimized
- 2. AWS Data Exchange
- 3. AWS Transfer family(Correct)
- 4. Datasync

*Correct Answer(s):*
 3. AWS Transfer family

**Explanation:**
AWS Transfer Family is a managed file transfer service, and you can transfer data using existing SFTP, FTP, FTPS, and AS2 clients into and out of AWS Storage Services like S3 and EFS. Datasync is optimized for moving large amounts of data using a Datasync agent. AWS Data Exchange is a comprehensive collection of third-party datasets that customers can subscribe to and use. Snowball Edge Compute Optimized is a secure, rugged device that brings AWS computing and storage capabilities, such as Amazon EC2, Amazon EBS, Amazon S3, AWS IoT Greengrass, AWS Lambda functions, and AWS IAM to your edge environments for machine learning, data analytics, processing, and local storage. Refer to SAA C03 - Services Summary lecture/article in the course

## Question 29:

 A multi-AZ RDS setup consists of: Primary instance, Standby instance and a Read-replica. If the standby instance is not able to catch-up, what is the impact to transactions in primary?

- 1. Transaction are impacted only if you configured it for Asynchornous Replication
- 2. Transactions are impacted(Correct)
- 3. Transactions are not impacted
- 4. Transaction are impacted only if you configured it for Synchornous Replication

*Correct Answer(s):*
 2. Transactions are impacted

**Explanation:**
RDS uses synchronous replication between primary and standby systems for multi-AZ high availability. If the standby is slow, transactions will take longer to complete. You don't want a smaller-sized standby instance as it won't be able to keep up with changes in the primary. This is the reason why primary and standby systems are similarly sized instances.

## Question 30:

 Under AWS Shared Responsibility Model, who is responsible for applying critical security patches on EC2 instances?

- 1. AWS
- 2. AMI Provider
- 3. EC2 Support
- 4. Customer(Correct)

*Correct Answer(s):*
 4. Customer

**Explanation:**
Infrastructure as a Service (IaaS) products like EC2 that are deployed a customer are a responsibility of the customer.  They are responsible for management of guest operating system included applying patches.

## Question 31:

 You need to move an EBS volume from one instance and attach it to another EC2 instance running in a different availability zone in the same region.  What steps do you need to perform?

- 1. Stop the instance and restart it and it will force a move a new to a different AZ
- 2. Stop the original instance, take a snapshot of the EBS Data volume, create a new volume using the snapshot in the new AZ and mount it to the EC2 instance(Correct)
- 3. Detach from original instance, change AZ for the EBS Volume and use it in the new instance
- 4. Detach from original instance and attach the EBS volume to the new instance

*Correct Answer(s):*
 2. Stop the original instance, take a snapshot of the EBS Data volume, create a new volume using the snapshot in the new AZ and mount it to the EC2 instance

**Explanation:**
EBS volumes are specific to a particular Avaialbility Zone.  If you need the data in a different Availability Zone or Region, you have to first snapshot the original volume and then use it in another availability zone within the same region.  You can also copy the snapshot to a different region if needed.

## Question 32:

 Your application has a large worldwide user base, and you would like to keep the user profile in the region closest to the user. Any changes to the user profile need to be replicated in other regions. The changes to the user profile can happen in any of the regions. Which one of these options would meet this requirement?

- 1. Multi-region RDS Read-replicas
- 2. Aurora Global Database
- 3. DynamoDB Global Table(Correct)
- 4. S3 with Cross-region replication and Data Sync

*Correct Answer(s):*
 3. DynamoDB Global Table

**Explanation:**
DynamoDB Global Tables are designed for massively scaled multi-master replication across AWS regions. This takes care of automatically replicating changes happening in different regions. You can use this to provide low latency access to data irrespective of where the user is located. Aurora Global Database maintains a low latency read replica of the database in other regions. However, all writes are performed in the primary database. This question calls for the ability to write to different regions. S3 Cross Region Replication is meant for one-way synchronization between two S3 regions. DataSync can be used to replicate data to multiple S3 buckets. But S3 replication and DataSync are one-way and do not support two-way synchronization.

## Question 33:

 An architect must implement the WORM (write once read many) paradigm for data stored in S3. The data needs to be protected for an undetermined amount of time. Which option would you use? [Choose two]

- 1. Use legal hold(Correct)
- 2. Ensure S3:PutObjectLegalHold permissions privileges are limited to people with a business need(Correct)
- 3. Configure the Object Lock retention period in Compliance Mode for each object
- 4. Configure the Object Lock retention period in Governance Mode for each object
- 5. Put a Deny All resource-based policy on the S3 buckets

*Correct Answer(s):*
 1. Use legal hold2. Ensure S3:PutObjectLegalHold permissions privileges are limited to people with a business need

**Explanation:**
Legal hold is more appropriate here when data needs to be retained for an unknown time. The s3:PutObjectLegalHold permission must be limited to people with a business need, as a person with this permission can remove a legal hold and would be able to remove the object if they also have the delete permission. Governance mode needs a retention period, and in addition, users with S3:ByPassGovernanceRestriction on the bucket would be able to remove the object if they also have the delete permission. The Deny All permission may be too restrictive as it will prevent even reads. Compliance mode changes are permanent and not suitable for the requirement with an undetermined retention period.Refer to S3 Object Lock lecture/article in the course

## Question 34:

 You want to reduce the cost of a workload comprising a mix of EC2, Lambda, and Fargate Containers. The workload resource requirement is expected to remain stable for the next year. Which of the following would you choose?

- 1. Spot Instances
- 2. Savings Plan(Correct)
- 3. On-demand
- 4. Reservation

*Correct Answer(s):*
 2. Savings Plan

**Explanation:**
Savings Plan. With Compute Savings Plan, you can get a significant discount (up to 66%) on any compute services such as EC2, Lambda, and Fargate Containers. So, the compute savings plan applies to both server-based and serverless computing. Reservation applies only to EC2 instances and does not cover serverless usage. Spot purchase is available only for EC2 instances and does not apply to serverless computing. On-demand is the default option. For long-term usage of 1-year or more, the Savings plan offers significant savings over on-demandKnowing what purchasing option to use is an important architectural decision - Spot, Savings Plan, Reserved Instances, On-demandPlease watch my YouTube hands-on tutorial on this topicAWS Pricing Calculation Tutorial - Spot, Savings Plan, Reserved Instances, On-demand - YouTube (30 minutes)https://www.youtube.com/watch?v=sb266536q_k

## Question 35:

 A fault-tolerant NoSQL Database application needs to support Reads in excess of 100,000 IOPS.  Which one of these instance types can meet this requirement at a lower cost?

- 1. General Purpose EBS Volume
- 2. Provisioned IOPS EBS Volume
- 3. Instance Store with SSD storage(Correct)
- 4. Instance Store with Magnetic storage

*Correct Answer(s):*
 3. Instance Store with SSD storage

**Explanation:**
Instance Store volumes with SSD storage can provide high IOPS, and they are often more cost-effective than EBS volumes as storage pricing is included in the instance hourly cost. However, it's important to note that data on instance store volumes is ephemeral and will be lost if the instance is stopped or terminated. The question states that the NoSQL database is fault-tolerant, and most likely has replication and backups to handle storage failure.Provisioned IOPS EBS Volume option allows you to provision a specific level of IOPS for your EBS volumes. The newer io2 Block Express volumes support up to 256000 IOPS, at a higher cost. General Purpose EBS volume supports a maximum of 16,000 IOPSInstance Store with Magnetic storage generally has lower performance compared to SSD. This option may not be suitable for meeting the high IOPS requirement.

## Question 36:

 You are using a Network Load Balancer to host an internet-facing application. The application needs to be accessible only from specific CIDR Blocks. Where would you enforce this policy? (Choose Three)

- 1. Network Load Balancer Security Group(Correct)
- 2. AWS Shield Advanced
- 3. EC2 Instance Security Group(Correct)
- 4. Web Application Firewall
- 5. Network ACL of the subnet where load balancer nodes are located(Correct)

*Correct Answer(s):*
 1. Network Load Balancer Security Group3. EC2 Instance Security Group5. Network ACL of the subnet where load balancer nodes are located

**Explanation:**
Network Load Balancer has introduced support for security groups as of August 2023. This enhancement allows you to restrict access based on CIDR blocks. In addition, when Client IP Preservation is enabled, you can also apply restriction at the EC2 instances based on the requester's IP address, leveraging the EC2 instance security group.You can add a rule to the security groups associated with your EC2 instances that references the security group associated with your Network Load Balancer. This allows clients to send traffic to your targets through your load balancer, but prevents them from sending traffic directly to your targetsThese security group controls are applicable across all three load balancer types—Classic, Application, and Network Load Balancers. Additionally, you can enforce these controls in the Network ACL associated with the load balancer subnets.Web Application Firewall allows for access limitation by IP address. However, it's important to highlight that WAF integration is exclusive to Application Load Balancer, CloudFront distribution, and API Gateway.For comprehensive security measures, Shield Advanced delivers automatic protection against layer 3 and layer 4 DDoS-type attacks.For more details, refer to the NLB official documentation: https://docs.aws.amazon.com/elasticloadbalancing/latest/network/load-balancer-security-groups.html

## Question 37:

 A multi-AZ RDS setup consists of: Primary instance, Standby instance and a Read-replica. If the read-replica is not able to catch-up, what is the impact to transactions in primary?

- 1. Transaction are impacted only if you configured it for Asynchornous Replication
- 2. Transactions are not impacted(Correct)
- 3. Transactions are impacted
- 4. Transaction are impacted only if you configured it for Synchornous Replication

*Correct Answer(s):*
 2. Transactions are not impacted

**Explanation:**
For multi-AZ high availability, RDS uses synchronous replication between primary and standby systems.  If standby is slow, transactions will take longer to complete.  RDS Read Replica on the other hand uses asynchronous replication and any slowness in Read Replica instance would simply cause data lag in the read - replica.  Transactions in primary is not impacted

## Question 38:

 A sports broadcaster has a collection of current and historical videos that must be immediately accessible when needed. The access pattern is unclear. Which S3 option meets the requirement while reducing the storage cost?

- 1. S3 Lifecycle Policies
- 2. Standard Infrequent Access
- 3. Standard
- 4. Intelligent Tiering(Correct)

*Correct Answer(s):*
 4. Intelligent Tiering

**Explanation:**
With intelligent tiering, S3 automates the process of moving objects to the most cost-effective access tier based on access frequency. There are no retrieval fees for objects in intelligent tiering. Standard is for frequently accessed data and is the most expensive option. Standard IA is meant for infrequently accessed data; however, when data in standard IA is frequently accessed, the retrieval fees might exceed the storage costs. S3 Lifecycle policies are suitable when access pattern is defined using time periods.

## Question 39:

 Application availability needs to be increased from 99.95% to 99.99%. To meet this increased availability requirement, you will notice the below trends. However, one of the choices is incorrect. Which one is it?

- 1. Increase in frequency of application changes(Correct)
- 2. Reduce time to recover from failures
- 3. Increase in overall solution cost
- 4. Increase in automation

*Correct Answer(s):*
 1. Increase in frequency of application changes

**Explanation:**
99.95% availability indicates a maximum of 4 hours and 22 minutes of disruption per year. At 99.99% availability, only 52 minutes of disruption per year is allowed. Increasing application availability generally increases solution cost. You would need a higher level of automation for automated recovery; manual intervention introduces delay and errors. You would also need to reduce the time for recovery to meet the high availability goals. The frequency of application changes generally decreases as every change introduces a risk of service disruption

## Question 40:

 You are planning to design a Chat application using AWS Lambda.  There are two parts to this application.  First part receives messages from a specific port.  Second part forward the message to its destination.  You want to implement these as two separate Lambda functions.  What is best mechanism do this?

- 1. Use Lambda pattern templates to leverage best practices when designing applications that listen and respond to network port requests
- 2. Lambda makes it very easy to listen on input ports and process the requests
- 3. Lambda cannot listen on input ports. You can use API Gateway to listen, receive requests and then invoke appropriate Lambda function(Correct)
- 4. Use Lambda to receive messages on specific port and forward it to SNS to fan out messages to intended recipients

*Correct Answer(s):*
 3. Lambda cannot listen on input ports. You can use API Gateway to listen, receive requests and then invoke appropriate Lambda function

**Explanation:**
Inbound network connections are blocked by AWS Lambda. However, outbound calls are allowed from Lambda. In this case, we can use an API Gateway to listen and receive inbound requests. The API Gateway would then invoke a Lambda function to process the request

## Question 41:

 You have a home grown application that uses a TCP port for communication.  The messages carry a custom payload that is unique for your application.  To support the growing needs, you are planning to add several new EC2 instances and you would like to load balance the application with ELB.  Which elastic load balancer is suitable for this?

- 1. Network Load Balancer(Correct)
- 2. Classic Load Balancer
- 3. Gateway Load Balancer
- 4. Application Load Balancer

*Correct Answer(s):*
 1. Network Load Balancer

**Explanation:**
Network Load Balancer is the recommended option.  Classic Load Balancer also supports TCP layer load balancing; however for newer applications, Network LB is recommended.  AWS currently recommends Classic LB only for EC2-Classic network.  ALB is an application layer load balancer.

## Question 42:

 You want to put restrictions in a S3 bucket so that only your EC2 instances can access the bucket. EC2 instances access S3 bucket using a VPC endpoint.  What condition can you use in the S3 Bucket Policy to restrict access?

- 1. VPC Endpoint ID (Correct)
- 2. Public or Private IP Address
- 3. Private  IP Address of EC2 instance
- 4. Public IP Address of EC2 instances

*Correct Answer(s):*
 1. VPC Endpoint ID 

**Explanation:**
With VPC Endpoints, the EC2 instance can access S3 using a Private IP address, and the traffic is routed inside the AWS private network. In the S3 bucket policy, you can put a policy to limit access only via VPC Endpoint IDNote: Private IP Addresses are not supported in policies as multiple VPCs can share the same CIDR block

## Question 43:

 For your EC2 Linux instance, there are two security groups attached.  First security group allows SSH access from 10.0.0.55/32.  Second security group allows SSH access from 10.0.0.0/24.  What is the net effect?

- 1. Access is allowed from any IP address that belongs to 10.0.0.0/24 network(Correct)
- 2. Access is allowed from 10.0.0.0 IP address
- 3. It depends on order of the rule in the security group
- 4. Access is allowed only from 10.0.0.55 IP address

*Correct Answer(s):*
 1. Access is allowed from any IP address that belongs to 10.0.0.0/24 network

**Explanation:**
All requests coming from 10.0.0.0/24 subnet is allowed access to the instance.  Since 10.0.0.55 is also part of the same subnet/network it will be able to access as well. Note: 10.0.0.0 is not a valid IP address on its own.  It is used for identifying a network 10.0.0.0/24.

## Question 44:

 You have encrypted all your data using the KMS-Customer Master Keys (CMK). The corporate policies require periodic master key rotation. How often is the KMS-CMK rotated?

- 1. Every month when automatic rotation is enabled
- 2. Every three years
- 3. Every year
- 4. Every year when automatic rotation is enabled(Correct)

*Correct Answer(s):*
 4. Every year when automatic rotation is enabled

**Explanation:**
You need to enable automatic rotation of KMS – Customer Managed Keys. Once the rotation is enabled, AWS automatically rotates the key every year.Please refer to At-rest Encryption and Key Rotation lecture/article in this course.

## Question 45:

 You plan to migrate over 100 TB of data from your data warehouse system to the Amazon Redshift database. The network bandwidth from on-premises to the internet for this data migration is 250 Mbps. What option would you use to transfer data to AWS quickly?

- 1. Use Direct Connect for large data transfers
- 2. Use DataSync
- 3. Use Snowball Appliance(Correct)
- 4. Use S3 multi-part transfer to upload to S3 and then load the data to Redshift

*Correct Answer(s):*
 3. Use Snowball Appliance

**Explanation:**
Snowball appliance provides a convenient mechansim to transfer petabyte scale data in and out of AWS.  Snowball is a tamper resistant, secure appliance with 256 bit encryption and data is physically shipped to and from AWS. With a 250 Mbps link, it will take 40 days to transfer 100 TB data. Whereas, snowball turn around time is less than 1 week. Refer to Data Transfer and Migration Scenarios videos. https://aws.amazon.com/blogs/storage/best-practices-for-accelerating-data-migrations-using-aws-snowball-edge/

## Question 46:

 Your application needs to be accessible only inside a specific country. Which service or capability would you use to enforce this policy?

- 1. Network ACL
- 2. Route 53 Geoproximity Routing
- 3. Web Application Firewall(Correct)
- 4. Shield Advanced

*Correct Answer(s):*
 3. Web Application Firewall

**Explanation:**
Web Application Firewall allows you to enforce country-specific rules. You can block or allow traffic from specific countries. Route 53 Geolocation and Geoproximity routing only handles DNS queries. It does not protect your application from requests coming from other countries. Network ACL is useful for blocking traffic based on IP address and CIDR Blocks. This approach requires you to maintain the IP Address list by country and can be a lot of work. Shield Advanced protects a resource against Layer 3 and 4 attacks and is not the correct solution for this question

## Question 47:

 Which of these options maintains a scaled-down infrastructure in another region and requires only scaling after a disaster?

- 1. Multi-site Active/Active
- 2. Warm Standby(Correct)
- 3. Pilot Light
- 4. Backup and Restore

*Correct Answer(s):*
 2. Warm Standby

**Explanation:**
Warm Standby maintains a continuously replicated copy of data, and a scaled-down infrastructure is always running for the rest of the components (for example, app servers, web servers, and so forth). After a disaster, we only need to scale the rest of the services to handle the traffic. Warm Standby can meet more stringent RTO/RPO in minutes. Backup and Restore only maintains a backup in another region. After a disaster, we need to restore the data and bring the entire infrastructure up in the second region, so the RTO/RPO is in hours. Pilot light maintains a continuously replicated copy of the data in another region; however, the rest of the infrastructure needs to be brought up after the disaster. So, the RTO/RPO is in 10s of minutes. Multi-site Active/Active is a zero-downtime solution with infrastructure in multiple regions. The application request is routed to any of the regions. This option can meet real-time RTO/RPO requirements.

## Question 48:

 You are consolidating data from multiple SaaS partners like Salesforce, SAP, and Zendesk. Which service would you use for this?

- 1. AWS EventBridge Partner Bus
- 2. AWS AppFlow(Correct)
- 3. AWS Step Functions
- 4. AWS AppSync

*Correct Answer(s):*
 2. AWS AppFlow

**Explanation:**
AWS AppFlow. AppFlow is a no-code solution to automate data flow by securely integrating third-party applications and AWS services and securely transferring data from SaaS applications like Salesforce, SAP, Zendesk, Slack, and ServiceNow. AppSync is used for building applications with serverless GraphQL and Pub/Sub APIs. EventBridge Partner Bus is useful for handling event-based integration. For example, a ticket created in Zendesk can trigger a workflow in your application. Since this question calls for data consolidation, we need a solution that pulls existing data and ongoing changes. AWS Step Functions is useful for orchestration; AppFlow provides a ready-to-use solution.

## Question 49:

 A company has a hybrid infrastructure with application hosted on-premises and on AWS.  They would like to direct 90% of the customer traffic to on-premises system with the remaining traffic routed to the new AWS cloud implementation.  To achieve this, which routing scheme can you use in Route 53?

- 1. Geolocation Routing
- 2. Latency Routing
- 3. Weighted Routing(Correct)
- 4. Geoproximity Routing

*Correct Answer(s):*
 3. Weighted Routing

**Explanation:**
Weighted routing allows you to assign weights to resource record sets. Route 53 answers DNS queries according to the specified weight

## Question 50:

 You want to track the memory utilization metrics for your EC2 instances.  Which one of these options can you use?

- 1. Configure CloudWatch Agent to collect Memory and Disk metrics(Correct)
- 2. Memory metrics are automatically published to CloudWatch logs
- 3. Memory metrics are automatically reported as part of EC2 Basic Monitoring
- 4. Memory metrics are reported when you enable EC2 Detailed Monitoring

*Correct Answer(s):*
 1. Configure CloudWatch Agent to collect Memory and Disk metrics

**Explanation:**
Memory utilization, swap file, and page file metrics are not automatically provided in CloudWatch. You need to install the CloudWatch Agent in the EC2 instance and configure it to publish memory and disk metrics to CloudWatch .https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/mon-scripts.htmlhttps://docs.aws.amazon.com/AmazonCloudWatch/latest/monitoring/Install-CloudWatch-Agent.html

## Question 51:

 Your Lambda function needs access to a private web end point available in your VPC.  What steps do you need to enable such an access?

- 1. Private VPC access is not allowed from Lambda
- 2. Setup a Route 53 private hosted zone and configure Lambda to use the private zone
- 3. Configure Lambda to run inside a private subnet of your VPC(Correct)
- 4. Setup Peering connection between Lambda System VPC and your Private VPC

*Correct Answer(s):*
 3. Configure Lambda to run inside a private subnet of your VPC

**Explanation:**
Configure Lambda to run inside a private subnet of your VPC. Lambda function can only access private resources inside your VPC when you configure it to run inside your VPC. You need to specify the VPC, private subnets, and Security group as part of the Lambda configuration

## Question 52:

 In your subnet, you have a Network ACL that has the following inbound rules: Rule #10: ALLOW SSH traffic from 0.0.0.0/0  Rule #20: DENY SSH traffic from 10.20.30.40/32.  A server with IP Address 10.20.30.40 makes an SSH request to an instance located in the above subnet.   What is the behavior observed?

- 1. SSH traffic is denied from anywhere
- 2. SSH traffic is allowed from anywhere(Correct)
- 3. SSH traffic is denied from 10.20.30.40/32
- 4. 10.20.30.40/32 is not a valid source and ACL rule cannot be saved

*Correct Answer(s):*
 2. SSH traffic is allowed from anywhere

**Explanation:**
ACL Rules are processed in increasing Rule # order.  First rule that matches the request grants or denies access to the request.  Make sure you put any specific DENY rules first before allowing wider access

## Question 53:

 Which of these services are global? (Choose Two)

- 1. Machine Learning
- 2. CloudFront(Correct)
- 3. S3
- 4. IAM(Correct)

*Correct Answer(s):*
 2. CloudFront4. IAM

**Explanation:**
CloudFront is global. IAM resources are global. S3 is sometimes called a global service; however, the buckets and data are stored in a specific region you select. Remember, for data residency compliance, the customer’s data needs to be stored only in the region that customer selects. The only reason why S3 is called global is bucket name needs to be globally unique (i.e., two buckets in AWS cannot have the same name)

## Question 54:

 An organization has several RDS databases, DynamoDB tables, and EFS file shares. The data needs to be backed up automatically, and a copy must be maintained in the disaster recovery region. Which solution would you use?

- 1. Use AWS Backup to set up backup policies, automate the process, and maintain a copy in the DR site(Correct)
- 2. Upload backups to S3 and configure S3 Cross Region Replication
- 3. Use CloudFormation to configure each database and resource to take periodic snapshots and for maintaining a copy in the DR site
- 4. Schedule CloudWatch Events/Eventbridge to automate snapshots and for copying to the DR region

*Correct Answer(s):*
 1. Use AWS Backup to set up backup policies, automate the process, and maintain a copy in the DR site

**Explanation:**
We can centrally manage the backup policies and automate the process using the AWS Backup service. In addition, AWS Backup can also maintain a copy of the backup in a disaster recovery region. While scheduling CloudWatch Events is feasible, you have to create and maintain scheduled jobs for each database and account. AWS Backup service makes the task much easier. S3 CRR is useful, but you have to configure jobs to copy to the S3 bucket and set up replication

## Question 55:

 KMS - AWS Managed Keys are automatically rotated

- 1. Every year when automatic rotation is enabled
- 2. Every year(Correct)
- 3. Every Month
- 4. Every three years

*Correct Answer(s):*
 2. Every year

**Explanation:**
AWS Managed Keys are automatically rotated every year.Refer to At-rest Encryption and Key Rotation article/lecture

## Question 56:

 Your legal department has asked your team to ensure that project documents are not deleted or tampered with.   They have further asked for a three year retention window.  Your team is currently using Glacier for storing the project documents.  What option would you pick to enforce this policy?

- 1. Put a Deny All resource-based policy on the S3 buckets
- 2. Configure Object Lock legal hold on all the buckets
- 3. Configure Object Lock retention period of three years in Governance Mode
- 4. Configure Object Lock retention period of three years in Compliance Mode(Correct)

*Correct Answer(s):*
 4. Configure Object Lock retention period of three years in Compliance Mode

**Explanation:**
Configure a retention period of three years in Compliance Mode for each object. This will ensure current object versions are protected from modification and deletion. Governance mode is not the right choice as administrators, and other users with S3:* permission on the bucket would be able to remove the object version. A legal hold may be possible; however, people with s3:PutObjectLegalHold permission can disable the legal hold and then delete the object. The Deny All permission may be too restrictive as it will prevent even reads.Refer to S3 Object Lock article/lecture

## Question 57:

 Multiple applications in different accounts within an enterprise upload data to a central S3 bucket. What security configuration would you use for the bucket?

- 1. Ensure uploads are allowed for authorized accounts in the organization, and the object ACL is configured to allow full access to the bucket owner account
- 2. Ensure uploads are allowed for authorized accounts in the organization
- 3. Disable ACL-based permissions management for the bucket and ensure uploads are allowed only for authorized accounts in the organization(Correct)
- 4. Ensure all accounts in the organization have permission to upload objects

*Correct Answer(s):*
 3. Disable ACL-based permissions management for the bucket and ensure uploads are allowed only for authorized accounts in the organization

**Explanation:**
Disable ACL-based permissions management for the bucket and ensure uploads are allowed only for authorized accounts in the organization. ACL is a legacy way of managing permissions and is problematic with cross-account upload scenarios. A bucket owner cannot read the object in the bucket unless the uploading account grants permissions using ACL. When you disable Object ACL, the bucket owner automatically owns all the objects in the bucket, and permission can be effectively managed using identity-based and resource-based policies

## Question 58:

 Your application is seeing a lot of traffic from mobile devices. You would like to optimize the latency to ensure the app is responsive. Which of the following hosting options would you use for this usage?

- 1. AWS Local Zones
- 2. ECS Anywhere
- 3. AWS Wavelength(Correct)
- 4. AWS Outposts

*Correct Answer(s):*
 3. AWS Wavelength

**Explanation:**
AWS Wavelength. If your application receives a lot of traffic from mobile devices, you can reduce latency and improve performance by hosting the containers in AWS Wavelength. This is an edge infrastructure managed by AWS, and your EC2 instances are embedded within 5G communication providers. Wavelength is a logical extension of a Region and is managed through the AWS region. AWS Local Zones are additional AWS locations closer to large population centers and industries. So, you can run latency-sensitive applications in AWS Local Zones. Outpost is an AWS-managed infrastructure running in your on-premises data center. This option is useful when you need low-latency access to AWS services for your on-premises systems. With ECS Anywhere, you can use ECS to manage containers on customer-managed on-premises infrastructure or even a multi-cloud setup

## Question 59:

 Your customers are complaining about slow database queries. The data analytics team runs many of these long-running queries, and these queries access historical data.These queries are also slowing down the application. The application requires access to up-to-date data.What solution would you propose? (Choose Two)

- 1. Scale up the database instances and explore the Provisioned IOPS storage to ensure consistent performance
- 2. Ensure application queries continue to use the primary database(Correct)
- 3. Add read replicas and configure data analytics queries to use the read-replica(Correct)
- 4. Migrate database to a NoSQL database to better support the performance requirements
- 5. Add read replicas and configure both data analytics queries and application queries to use the read-replica

*Correct Answer(s):*
 2. Ensure application queries continue to use the primary database3. Add read replicas and configure data analytics queries to use the read-replica

**Explanation:**
With RDS read replicas, we can offload long-running read-only queries to the read replicas. This approach will free up resources in the primary database. Since data analytics queries require access only to historical data, we can easily support these queries using one or more read replicas. The application requires access to the most up-to-date data and must continue using the primary database. Migration to NoSQL is not required as it would require complex application changes

## Question 60:

 You have a data warehouse system that stores 100s of columns and analytic queries pull only a small set columns across millions of rows.  With Redshift Datastore, what are the benefits for this use case? (Choose Two)

- 1. Redshift supports very large number of read and write requests
- 2. Redshift uses columnar storage and can offer substantial reduction in I/O when compared to other database technologies(Correct)
- 3. Upto 1/10th the cost of other warehouse technologies(Correct)
- 4. Redshift is optimized for retrieving all columns

*Correct Answer(s):*
 2. Redshift uses columnar storage and can offer substantial reduction in I/O when compared to other database technologies3. Upto 1/10th the cost of other warehouse technologies

**Explanation:**
Redshift is amazon's columnar storage offering. It offers high level of data compression and is optimized for reading specific columns.  It designed for scale-out processing and cost-effective when compared to other traditional data warehouse solutions

## Question 61:

 What capability can you use for auditing inbound and outbound traffic in your VPC?

- 1. CloudWatch Log
- 2. CloudTrail Log
- 3. VPC Flow Log(Correct)
- 4. S3 Server Access Logs

*Correct Answer(s):*
 3. VPC Flow Log

**Explanation:**
VPC Flow Log is used for monitoring traffic at VPC, Subnet or at individual interface level.  You can use this for troubleshooting network issues and for monitoring traffic in and out of your VPC.  Cloud Watch Log is a generic capability for log aggregation, filtering and monitoring.  You can use this to publish your own logs.  Cloud Trail Log is used for monitoring AWS resources and changes made to the resources through API, SDKs, Command Line tools.  Access Log is used for monitoring requests that are made to S3 bucket

## Question 62:

 Which service would maintain the certificates needed to enable SSL/TLS encryption (HTTPS) for your website?

- 1. KMS
- 2. KMS-Customer Managed Key
- 3. AWS Secrets Manager
- 4. AWS Certificate Manager(Correct)

*Correct Answer(s):*
 4. AWS Certificate Manager

**Explanation:**
Use AWS Certificate Manager to provision, manage, and deploy SSL certificates. ACM-issued certificates are automatically renewed and bound with ACM integrated services like ELB, CloudFront, API Gateway, etc. KMS is used for application data encryption and at-rest encryption. Secrets Manager is more commonly used for storing passwords, access key credentials, and Keys needed to access third-party APIs

## Question 63:

 You are developing a mobile application that needs to scale to very large number of concurrent users with a consistent millisecond latency.  What backend store can you use for storing user sessions? (Choose Two)

- 1. ElastiCache(Correct)
- 2. Relational Database Service
- 3. DynamoDB(Correct)
- 4. ElasticSearch

*Correct Answer(s):*
 1. ElastiCache3. DynamoDB

**Explanation:**
DynamoDB provides consistent, single-digit millisecond latency at any scale. ElastiCache provides sub-millisecond latency to power real-time applications.

## Question 64:

 A company has several EC2 instances and employees access them over the internet using Public IP address.  When instances are stopped and started, employees are complaining that they are not able to connect.  What option would you recommend?

- 1. Configure EC2 settings to assign same Public IP Address when instance is stopped and started.
- 2. Instead of public IP address, use Elastic IP Address for the instances.  This will ensure IP address remains the same for the instances between stop and start cycles
- 3. Public IP Address does not change when instance is stopped and started. Most likely instance was terminated and relaunched
- 4. Use Bastion Host with an Elastic IP Address.  Ask employees to first connect to Bastion Host and then logon to their instance using Private IP Address(Correct)

*Correct Answer(s):*
 4. Use Bastion Host with an Elastic IP Address.  Ask employees to first connect to Bastion Host and then logon to their instance using Private IP Address

**Explanation:**
Public IP Address is optional and when requested, AWS assigns one from its pool of IP addresses.  When an instance is stopped, public IP address is released. Instance gets a new public IP address when it is restarted.  Elastic IP addresses can be used for assigning static public IP address to the instances; however, AWS limits each account to 5 Elastic IPs per region and you need to justify to AWS if you need additional IP Addresses.  Bastion Host with a single well-known access point is the recommended option and you can let your customers access the EC2 instances using private DNS name or private IP Addresses.  Bastion Host also improves security posture as it reduces attack surface by keeping your EC2 instances in private subnet.  You can tighten instances’ security group to allow access only from Bastion Host security group.  Private DNS Name and Private IP Address remains attached to the instance until the instance is terminated.

## Question 65:

 A media company has documents, videos, images and other paid content that is currently hosted in their own datacenter.  Content is personalized based on signed-on user.  Users are located world wide and they are complaining about timeouts and poor performance.  What options do you have to address this situation? (Choose Two)

- 1. Use ElastiCache to cache content at edge locations
- 2. Store media files and other static content in S3. Use Amazon CloudFront to cache at the edge location.  Dynamic and personalized content is not supported by CloudFront
- 3. Store media files and other static content in S3. Use Amazon CloudFront to handle all your application request (including personalized content)(Correct)
- 4. Migrate application to AWS and deploy across multiple regions.  Use Route53 latency based routing to direct customers to appropriate region(Correct)

*Correct Answer(s):*
 3. Store media files and other static content in S3. Use Amazon CloudFront to handle all your application request (including personalized content)4. Migrate application to AWS and deploy across multiple regions.  Use Route53 latency based routing to direct customers to appropriate region

**Explanation:**
CloudFront allows you to cache the content closest to your customer using AWS global Edge network. CloudFront Origin can be S3, applications hosted in AWS, and external applications hosted on-premises. CloudFront also supports dynamic content that is personalized based on signed-on user

## Question 66:

 A containerized application sees sustained high CPU and memory utilization. Which of these launch types may optimize the cost?

- 1. ECS Cluster with EC2 instance launch type(Correct)
- 2. Customer-managed infrastructure with EC2 instances
- 3. Any ECS Cluster launch type
- 4. ECS Cluster with Fargate launch type

*Correct Answer(s):*
 1. ECS Cluster with EC2 instance launch type

**Explanation:**
ECS Cluster with EC2 instance launch type. This option is cost-effective for workloads that require consistently high CPU and memory usage. The Fargate option is recommended when you don't want to manage the infrastructure. Customer-managed infrastructure with EC2 instances would require the customer to handle regular maintenance, patching, and monitoring. ECS is preferred as it can take of the undifferentiated heavy lifting

## Question 67:

 You are evaluating the current Disaster Recovery procedures for an organization.  Based on process and procedures, you notice that it may take up to 5 hours to restore services under a disaster scenario.  What industry term is used for disaster planning to capture this information?

- 1. Restore Time Objective
- 2. Recovery Point Objective (RPO)
- 3. Mean Time Between Failure
- 4. Recovery Time Objective (RTO)(Correct)

*Correct Answer(s):*
 4. Recovery Time Objective (RTO)

**Explanation:**
Recovery Time Objective captures time it takes to restore business processes after a disaster

