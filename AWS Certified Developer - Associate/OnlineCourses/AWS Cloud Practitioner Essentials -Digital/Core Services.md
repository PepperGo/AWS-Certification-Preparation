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





