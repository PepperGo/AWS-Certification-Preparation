## AWS Cloud Practitioner Essentials: Core Services  

### AWS Global Infrastructure  
AWS's global infrastructure can be broken down into three topics: regions, availability zones, and edge locations.  
#### Regions  
Regions are geographic areas that host two or more availability zones.

#### Availability Zones
AZs are a collection of data centers within a specific region. Each are isolated from one another but yet they are connected together by a fast, low-latency link.(Benefit: when common points of failures occur, it does not affect all of your availability zones because they are isolated.)  

Each availability zone is a physically distinct, independent infrastructure. They are also physically and logically separate.  
Each zone has their own discrete uninterruptable power supply, onsite back up generators, cooling equipment, and networking and connectivity.  

Isolating them protects from failures in other az's to ensure high availability, and makes it possible for the other az's to handle requests.  

AWS's best practice is to provision your data across multiple az's.  

#### Edge Locations
AWS edge locations host a content delivery network or CDN called Amazon CloudFront.  
CloudFront is used to deliver content to your customers. Requests for content are automatically routed to the nearest edge location so that the content is delivered faster to the end users.  

[Amazon CloudFront Edge Infrastructure](https://aws.amazon.com/cloudfront/details/)  


### Amazon Virtual Private Cloud(VPC)
#### Introduction
Amazon VPC is an AWS foundational service and integrates with numerous AWS services. (Amazon EC2, Amazon EMR, Amazon RDS...)

Amazon VPC
- allows to create a private network in the AWS cloud
  - Uses same concepts as on premise networking
- allows complete control of network configuration(IP address spaces, subnets, and routing tables)
  - Ability to isolate and expose resources inside VPC
- offers serveral layers of security controls(isolating subnets, defining access control lists, customizing routing rules)
  - Ability to allow and deny specific internet and internal traffic
- other AWS services deploy into VPC
  - Services inherent security built into network

#### Features
- Builds upon high availability of AWS Regions and Availablity Zones(AZ)  
  - Amazon VPC lives within a Region  
  - Can create multiple VPCs per account  
  
- Subnets(A VPC defines an IP address space that is then divided by subnets)  
  - Used to divide Amazon VPC  
  - Allows Amazon VPC to span multiple AZs  
  - Can be classified as public or private   
  - public(having direct access to the Internet; we need to attach an Internet gateway(IGW) to the VPC and update the route table of the public subnet to send non-local traffic to the Internet gateway)   
  - private(not having direct access to the Internet; NAT Gateway)    
  
- Route tables  
  - Control traffic between subnets and the Internet(By default, all subnets within a VPC can communicate with each other)  
- Internet Gateway(IGW)   
  - Allows access to the Internet from Amazon VPC  
- NAT Gateway   
  - Allows private subnet resources to access Internet  
- Network Access Control Lists(NACL)  
  - Control access to subnets; stateless  
  
 
#### Example VPC
Create a network that supports high availability and uses multiple subnets.  
1. Select a region(since VPC is region based)  
  select the Oregon Region(us-west-2)  
2. Create the VPC, and define the IP address space for the VPC
  create the vpc named Test-VPC, and 10.0.0.0/16 is the classless interdomain routing(CIDR) format means having more than 65,000 IP addresses to use in the VPC  
3. Create a subnet and specifiy the AZs
  create a subnet named Subnet A1, assigned an IP address space(CIDR is 10.0.0.0/24) that contains 256 IP addresses, and specify that this subnet will live in an Availability Zone A.  
4. Create other subnets  
  create another subnet in Availablity Zone A called Subnet B1, assin an IP address space(CIDR is 10.0.2.0/23) that contains 512 IP addresses.
5. Create an Internet gateway(IGW)  
  create an Internet gateway called Test-IGW, Subnet A1 becomes a public subnet where non-local traffic is routed through the Internet gateway. Subnet A2 becomes will be the private subnet that is isolated from the Internet.  
  
[Amazon Virtual Private Cloud](https://aws.amazon.com/vpc/?hp=tile&so-exp=below)  

### Security Groups
AWS provides virtual firewalls that can control traffic for one or more instances, called security groups.  
You can control accessibility to your instances by creating security group rules.  
These security groups can be managed on the AWS management console.  

### Compute Services  
AWS offeres flexibility and cost effectiveness. Scalability is built into our compute services.  
Amazon EC2: allows you complete flexibility to run applications at any scale.  
Amazon Lambda: allows you run code without provisioning or managing servers.  
Amazon Lightsail: simple website or e-commerce applications  
Amazon ECS: supports Docker containers and allows you to easily run applications on a managed cluster of Amazon EC2 instances.  
...  

### Amazon Elastic Compute Cloud(EC2)  
EC2: Elastic Compute Cloud
- Elastic  
  - if properly configured, you can increase and decrease the amount of servers required by an application automatically according to the current demands on that application.(Stop calling them servers, use the name of Amazon EC2 instances)   
- Compute  
  - Compute refers to the compute, or server, resources that are being presented(Application Server, Web Server, Database Server, Game Server...)  
- Cloud  
  - Cloud refers to the fact that these are cloud-hosted compute resources  
  
#### Amazon EC2 Instances
- Pay as you go  
- Broad selection of HW/SW  
- Global hosting  

[Amazon EC2](aws.amazon.com/ec2)  

#### How to build and configure and EC2 instance  
- Login in AWS Console  
- Choose a region  
- Launch EC2 Wizard  
- Select Amazon Machine Image(AMI)(Software)  
- Select instance type(Hardware)  
- Configure network  
- Configure storage  
- Configure tags  
- Configure Sercurity Group  
- Configure key pairs(download private key, eg: ec2-demo.pem)  
- Launch & Connect  

#### How to access EC2 Instance
- Description -> public DNS(IPv4) and public IPv4 IP address  
- puttygen.exe -> ec2-demo.pem -> save private key -> ec2-demo.ppk
- putty.exe -> user: EC2-user@+DNS -> select SSH -> Auth -> Browse -> private key file -> ec2-demo.ppk -> open  
- login in  

### AWS Lambda  
AWS Lambda is a compute service that lets you run code without provisioning or managing service. AWS Lambda executes code only when needed and scales automatically to thousands of requests per second.  Pay as you go -> ideal for varibale and intermittent workloads.  

- Fully-Managed serverless compute  
- Event-driven execution  
- Sub-second metering  
- Multiple languages supported  

AWS Lambda is intended to support serverless and microservices applications.  
#### Some configuration
disc space, memory allocation, execution time, 
#### Create a Lambda Function
AWS Lambda -> Create Function page console -> Create Function -> Configuration

Real-Time Image Processing  
Extract, Transform, Load piplines  
Microservices backend  

### AWS Elastic Beanstalk
#### What is Elastic Beanstalk?
- 1. Platform as Service(have the whole infrastructure and the whole platform that can put code over the system as required)  
- 2. Allows quick deployment of your applications  
- 3. Reduces management complexity  
- 4. Keep control in your hand(also can have full control like instance type. database, adjust Auto Scaling, update application, access server log files, enable HTTPS on the load balancer...)  
- 5. Supports a large range of platforms(Package Builder, Single Container/Multicontainer/Preconfigured Docker, Go, Java SE, Java with Tomcat, .NET on Windows Server with IIS, Node.js, PHP, Python, Ruby)  

#### Components
- 6. Easily Implemented  
Elastic Beanstalk provides all the application service, HTTP service, operating system, language interpreter, and the host.  
The only need that you have is to create your code, deploy it, prepare it according to the needs of your service.  

#### Deployment and Updates  
- 7. Update your application as easily as you deployed it  

#### Product Demonstration  
1. Start Service -> Go to dashboard and look for Elastic Beanstalk -> Create New Application -> name/description    
2. Create one environment -> Web server enviroment/Worker environment -> select -> Enviroment information/Base configuration  -> configure more options(Software, Instances, Database...) -> Create environment  
(Can also use command line interface and scripts)  


### Application Load Balancer  
#### What is the Application Load Balancer?  
- The second type of the Elastic Load Balancing(ELB) service  
- offer most of the features provided by the Classic Load Balancer, adds some important features and enhancements(Supported protocols, CloudWatch Metrics, Access Logs, Health Checks...)  

#### Why use the Application Load Balancer?  
##### THe ability to use containers to host your micro services and route to those applications from a single load balancer.  
Application Load Balancer allows you to route different requests to the same instance, but differ the path based on the port.  If you have different containers listening on various ports, you can set up routing rules to distribute traffic to only the desired backend application.  

**Key Terms**  
- Listeners  
  - A listener is a process that checks for connection requests, using the protocol and port taht you configure. The rules that you define for a listener determine how the load balancer routes requests to the targets in one or more target groups.  
- Target  
  - A target is a destination for traffic based on the established listener rules.
- Target Group  
  - Each target group routes requests to one or more registered targets using the protocol and port number specified. A target can be registered with multiple target groups. Health checks can be configured on a per target group basis.  
 
#### Features 
- Supported Protocols  
  - HTTP, HTTPS, HTTP/2, and WebSockets  
- CloudWatch Metrics  
  - Additional load balance metrics and Target Group metric dimension  
- Access Logs  
  - Ability to see connection details for WebSocket connections  
- Health Checks  
  - Insight into target and application health at more granular level  

#### Demonstration  
##### Create Load Balancer
- 1. AWS console -> EC2 Console -> already have two instances running  
- 2. side navigation pane -> Load Balancers -> Create Load Balancer -> Application Load Balancer   
- 3. Step 1: Configure Load Balancer(Basic Configuration, Listeners, Avaliability Zones. Tags) -> Next: Configure Sercurity Settings  
- 4. Step 2: Configure Security Settings -> Next: Configure Security Groups  
- 5. Step 3: Configure Security Groups -> Next: Configure Routing  
- 6. Step 4: Configure Routing(Target Group, Health Checks)  -> Next: Register Targets  
- 7. Step 5: Register Targets(Registered targets, Instances)  -> Next: Review
- 8. Step 6: Review -> Create  

##### Create Target Group
Because we have two targets that we want to check with this load balancer, in order to register the second target, we must first create a target group.  
- 1. side navigation pane -> Target Groups -> create target group
Then, check the configuration(both ports set up for the listening on the load balancer)  
- 2. View and Edit Rules -> THEN -> forware to demo2  -> update  

##### Test and Verify 


### Amazon Elastic Load Balancer  
#### Elastic Load Balancer(Classic Load Balancer)
The Classic Load Balancer is a distributed software load balancing service that enables the use of many helpful features packaged into a managed solution.   
Use Cases:  
- Access through single point  
- Decouple application environment  
- Provide high availability and fault tolerance    
- Increase elasticity and scalability  

#### Traffic Distribution  
The ability for the Elastic Load Balancing to distribute traffic depends on what type of request you are distributing.

- 1. HTTP/HTTPS
Elastic Load Balancing will use a **Least Outstanding** request for the back end instances.
- 2. TCP
Elastic Load Balancing will use a simple **round robin** for these reuqests.  

The Elastic Load Balancing also helps with distributing traffic across multiple Availability Zones.  

- 1. The Elastic Load Balancing provides a single exposed point of access for accessing your backend instances.  
  - The easiest way to do this would be to set up an alias record to point to your domain's CNAME to the endpoint for your Elastic Load Balancing.  
- 2. Sticky Sessions bind a user session for the duration of that session.   
  - Duration-based cookies or Application-controlled cookies  
  
#### Monitoring  
Elastic Load Balancing provides many metrics by dafault.  
These metrics allow you to:  
- View HTTP responses  
- See number of healthy and unhealthy hosts(done with a simple attempted connection or ping requests to the backend EC2 instance)  
- Filter these metrics based on Availability Zones or Load Balancer  

#### Scalability  
The Load Balancer helps with scalability by providing multizone load balancing, which enables to distribute traffic across multiple Availability Zones within your VPC.  
Also, the load balancer itself will scale based on the traffic pattern that it sees.  

##### With the Classic Load Balancer, you have the ability to create different types of load balancers.  
- Internet-Facing Load Balancers  
  - This gives you a pulicly resolvable DNS name that still allows your cross-zone balancing and allows you to route requests to the backend instances from your single exposed endpoint of your load balancer.  
- Internal Load Balancers  
  - This internal load balancer has a DNS name that resolves only to private nodes so it can only be accessed through the VPC. This provides a decoupling of your infrastructure within your VPC and allows for the scalability of both the front-end and the backend instances while the load balancer handles its own scaling.
  
##### Demonstration  
- 1. Have already launched an EC2 instance -> This EC2 instance is sitting in a VPC with an internet gateway attacked, and it is sitting in a public subnet(verify: take public IP address for this instance)  
- 2. Navigation Pane -> Load Balancing -> Load Balancers -> Create Load Balancer -> Classic Load Balancer 
- 3. Step 1: Define Load Balancer  
- 4. Step 2: Assign Security Groups 
- 5. Step 3: Configure Security Settings  
- 6. Step 4: Configure Health Check  
- 7. Step 5: Add EC2 Instances  
- 8. Step 6: Add tags  
- 9. Step 7: Review and Create  

Result: We can go to the instance through the load balancer instead of to the instance directly.  


### Auto Scaling  
#### What is Auto Scaling?
Auto Scaling helps you ensure that you have the correct number of Amazon EC2 instances available to handle the load for your application.   
#### Monitoring Resource Performance  
When running applications on EC2 instances, it's critical to monitor the performance of your workload using Amazon CloudWatch.   
However, CloudWatch will not add or remove EC2 instances, and this is where Auto Scaling comes into the picture.    

AutoScaling allows to add or remove EC2 instances based on conditions that you specify. And AutoScaling answers two critical questions:   
- How can I ensure that my workload has enough EC2 resources to meet fluctuating performance requirements?(Scalability)  
- How can I automate EC2 resource provisioning to occur on-demand?(Automation)    

#### Scaling  
##### Scaling in && Scaling out  
Auto Scaling can automatically adjust the number of EC2 instances running in your workload based on either conditions you define, CPU utilization over 80%, or scheduled.
- Scaling out  
  - Auto Scaling adds more instances  
- Scaling in  
  - Auto Scaling terminated instances  
  
#### How do you auto scale?   
There are three components required for auto-scaling.  
- Launch Configuration  
  - This is about defining what will be launched by Auto Scaling.(Such as which Amazon Machine Image to use, what instance type, security groups, or roles to apply to the instance)  
- Create Auto Scaling Group   
  - This is about defining where the deployment takes place and some boundaries for the deployment.(Where you define which VPC to deploy instances, in which load balancer to interact with, specify the boundaries for a group)  
- Auto Scaling policy  
  - This is about specifying when to launch or terminate EC2 instances.(schedue Auto scaling every Thursday at 3pm, or create conditions that define thresholds to trigger adding or removing instances)  

##### Dynamic Auto Scaling  
Condition-based policies make Auto Scaling dynamic and able to meet fluctuating requirements.  

- How does dynamic Auto Scaling work?  
One common configuration is to create CloudWatch alarms based on performance information from your EC2 instances or a load balancer.  
When a performance threshold is breached, a CloudWatch alarm triggers an Auto Scaling event which either scales out or scales in EC2 isntances in the enviroment.  

#### Demonstration  
1. Create a Launch Configuration  
AutoScaling -> Auto Scaling Group -> Create Launch Configuration  
2. Create an Auto Scaling Group  
3. Create an Auto Scaling policy  
4. Trigger Auto Scaling  

### Amazon Elastic Block Store(EBS)
EBS volumes can be used as a storage unit for your Amazon EC2 instances, so whenever you think you need disk space for your instances running on AWS, you can think about them.
- These volumes can be hard disks or SSD devices  
- Pay as you use  
- Persistent and customizable block storage for EC2 instances.  
- Replicated across multiple servers in the same Availability Zone  
- Backup using snapshots  
- Easy and transparent Encryption  
- Elastic volumes  

#### Demonstration  
1. EC2 -> ELASTIC BLOCK STORE -> Volumes -> Create Volume
2. Actions -> Attach Volume
3. Instances -> Connect  -> terminal cmd

### Amazon Simple Storage Service(S3)  
#### What is Amazon S3?
- Managed cloud storage service  
  - provides a simple API for storing and retrieving data  
  - data store in S3 isn't associated with any particular server, and you don't have to manage any infrastructure yourself  
- Store virtually unlimited number of objects
  - any data file, store as many as objects into S3
- Access any time, from anywhere  
  - S3 provides low-latency access to the data over the internet by HTTP or HTTPS  
  - You can also access S3 privately through a virtual private cloud endpoint  
- Rich security controls  
  - identity and access management policies, S3 bucket policies, and even per-object access control lists  
  - By default, none of the data is shared publicly  
  - Can encrypt data in transit and choose to enbale server-side encryption on your objects  
  
### How to store in S3?
1. create a bucket to hold data -> put data into bucket as an object -> need to specify a key(this key is used to retrieve object later).  
2. When you create a bucket in S3, it's associated with a particular AWS region. Whenever you store data in the bucket, it's redundantly stored across multiple AWS facilities within your selected region.  
3. S3 will automatically manage the storage behind your bucket even as your data grows.  
4. S3 will also scale to handle a high volume of requests.  

### How to access S3?  
- AWS management console  
- AWS CLI  
- AWS SDKs  
- Access data in your bucket directly via the rest endpoints  

### Common Use cases  
- Storing Application Assets  
- Static Web Hosting  
- Backup & Disaster Recovery  
- Staging area for Big Data  
- Many more...  

### Demonstration  
1. Amazon S3 Management Console -> Create bucket  
2. Click new created bucket -> upload/Create folder  
Can also use AWS CLI(s3 commands)  


### Amazon Glacier  
Amazon Glacier is in the storage service category, and it's low-cost data archiving solution.  
It's designed for storing cold data that's infrequently accessed, yet must be retained for business or legal reasons.  
- long-term storage at low cost  
  - Unlike with Amazon S3, Glacier is not designed to store data that has been accessed frequently. Instead, it is designed for long-term storage at low cost.    
- 99.999% durability  
  - By redundantly storing data in multiple facilities and on multiple devices within each facility  
- Access limited by vault policies  
  - Control access  
  
#### Three key terms  
- Archive  
  - An Archive is any object, such as a photo, video file, or document, that you store in Glacier.  
  - It's the base unit of storage in Glacier.  
  - Each Archive has its own unique ID and can also have a description if you can choose.  
- Vault  
  - A vault is a container for storing archives.  
  - When creating a vault, need to specify vault name and an AWS region in which you would like to create the vault.  
  - Vault access policies determine who can and cannot access the data stored in the vault, as well as what operations users can and cann't perform.  

#### How can you store and access data in Glacier?  
- AWS Management Console  
  - Limited operations available(creating and deleting vaults, creating and managing archive policies)  
- RESTful web service, Java or .NET AWS SDKs(via AWS Command Line Interface, AWS CLI)  
- Amazon S3(Using lifecycle policies)  

##### Lifecycle Policy 
A lifecycle policy that moves data as it ages from Amazon S3 into Glacier before it has been finally deleted.  

Amazon S3 Standard ->(30 days) -> Amazon S3 Standard - Infrequent Access -> 60 days -> Amazon Glacier ->365 days -> Deleted  
Then, if on an extremely rare occassion that preview is needed again, your application sess that the file is deleted and simply generates a new one.  

##### Retreving data in Glacier  
Data retrieval for Glacier is in minutes and hours rather than milliseconds like in S3.  
**Three Options for retrieving the data and with varying access times and costs:**  
1. Bulk(low cost, 5-12 hours)  
2. Standard(3-5 hours)  
3. Expedited(1-5 minutes)  

#### Storage Comparision  
##### Basic Differences
Amazon S3: high cost in storage, low cost in retrieval, low-latency access 
Amazon Glacier: low cost in storage, high cost in retrieval, low-cost, long-term storage  

##### Another difference - how data is Encryption  
Both Amazon S3 and Amazon Glacier can be stored over HTTPS, but with Glacier, any data archive there is encrypted by default.  
With S3, your application has to initiate the server-side encryption instead.  

#### Security with Amazon Glacier  
- Control access with AWS Identity and Access Management(IAM)  
- Glacier encrypts your data with AES-256  
- Glacier manages your keys for you  

#### Demonstration  
1. AWS Management Console -> Storage -> Glacier -> Create Vault  
2. Create  

### Amazon Relational Database Service(Amazon RDS)
#### Why Amazon RDS?
##### Challenges of running a standalone Relational Databases
- Server maintenance and energy footprint  
- Software install and patches  
- Database backups and high availability  
- Limits on scalability  
- Data security  
- OS install and patches  

Amazon RDS is a managed service that sets up and operates a relational database in the cloud.  
With Amazon RDS, your primary focus becomes data and optimizing application.  

#### Brief Overview of Amazon RDS  
The basic building block of Amazon RDS is the database instance.  
**A database instance** is an isolated database environment that can contain multiple user-created databases, and can be accessed by using the same tools and applications that you use with a standalone database instance.

- DB Instance Class  
  - CPU  
  - Memory  
  - Network performance  
- DB Instance Storage(types of disks)  
  - Magnetic  
  - General purpose(SSD)  
  - Provisioned IOPS  
  
Usually the database instance is isolated in a private subnet and is only made directly accessible to indicated application instances.   
Subnets in an Amazon VPC are associated with a single Availability Zone, so when you select the subnet, you're also choosing the Availability Zone or physical location for your database instance.  

##### Standby Copy 
1. Once configuredd, Amazon RDS automatically generates a standby copy of the database instance in another Availability Zone within the same Amazon VPC.  
2. After seeding the database copy, transactions are synchronously replicated to the standby copy.  
3. Running a database instance with Multi-Availability Zones can enhance availability during planned system maintenance and help protect databases against database instance failure and Availability Zone disruption.  
4. If the master database instance fails, Amazon RDS automatically brings the standby database instance online as the new master.  

##### Read Replicas
Updates made to the source database isntance are asynchronously copied to the **read replica isntance**.
- Asynchronous replication method used  
- Offload read queries from the master DB instance   
- Ideal for read-heavy database workloads  
- Read replica can be promoted to Master if needed  

Read replicas can be created in a different region than the master database.  
It can help:  
- 1. Satisfy disaster recovery requirements
- 2. Cutting down on latency by directing reads to a read replica closer to the user  

### Amazon DynamoDB  
#### What is DynamoDB?
- Amazon DynamoDB is a fully managed NoSQL database service.  
- Store as many items as you want  
- Items may have differing attributes  
- Low-latency queries  
- Scalable read/write throughput(auto-scaling)  

#### Partitioning  
Table data is partitioned and indexed by primary key.    
Two ways to retrieve data:  
1. Query by key to find items efficiently  
2. SCAN to find items by any attribute(less efficient, as DynamoDB will scan through all the items in the table to find the ones that match your criteria)  

#### How to build Key  
1. You can set up a simple primary key based on a single attribute of the data values with a uniform distribution, such as the GUID or other random identifiers.  
2. Alternatively, you can specify a compound key, which will be composed of a partition key and a secondary key.  

#### Demonstration  
1. AWS Management Console -> Amazon DynamoDB -> Create DynamoDB table  
2. Create DynamoDB table  
3. Create items  
4. Query items





































