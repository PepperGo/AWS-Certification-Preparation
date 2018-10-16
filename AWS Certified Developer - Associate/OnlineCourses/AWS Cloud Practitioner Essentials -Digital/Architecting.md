## AWS Cloud Practitioner Essentials: Architecting   

### Conents
* [Introduction to the Well Architected Framework](#introduction-to-the-well-architected-framework)  
* [Fault Tolerance and High Availability](#fault-tolerance-and-high-availability)  


### Introduction to the Well Architected Framework  
Well-Architected Framework:  
- Developed through reviewing customers' architectures on AWS.  
- Helps build the most   
  - Secure  
  - High-performing  
  - Resilient  
  - Efficient  
- Consistent approach for evaluating architectures  
- Five pillars with design principles  

The framework is designed to help you:  
- Build and deploy faster  
  - Stop guessing at capacity needs, and take advantage of automation opportunities  
- Lower or mitigate risks  
  - Understand where your risks are, and address them before going live  
- Make informed decisions  
  - Determine how architectural decisions might impact the performance and availability of your applications  
- Learn AWS best practices  
  - Access additional guidance through training and whitepapers  
  
#### The Five Pillars
- Operational Excellence  
- Security  
- Reliability  
- Performance Efficiency  
- Cost Optimization  


##### Operational Excellence Pillar  
The Operational Excellence pillar includes:  
- The ability to run and monitor systems to deliver business value    
- Continually improve supporting processes and procedures  

Design Principles:  
1. Perform operationas as code   
  - Treat your entire workload, including infrastructure, the same as you would application code.  
  - Use scripting and automation to trigger actions in response to events  
  - This will help you limit human error and enable consistent responses to events  
2. Annotate documentation  
  - Most often, documentation is created by hand, and doesn't automatically keep up with the pace of change. Seek to automate the documentation update process, to align with each change in environment.  
  - Also, you can use annotations as an input to your operations code.  
3. Make frequent, small, reversible changes  
  - Design workloads to allow components to be updated regularly.  
  - Make changes in small increments that can be reversed if they fail(without affecting customers when possible).  
4. Refine operations procedures frequently 
  - As you evolve your workload, evolve your procedures appropriately.  
5. Anticipate failure  
  - Research potential sources of failure so that they can be removed or mitigated.  
  - Test both failure scenarios, and failure response procedures.  
6. Learn from all operational failures  
  - Drive improvement through lessons learned from all operational events and failures
  
##### Security Pillar  
The security pillar includes the ability to protect information, systems, and assets while delivering business value through risk assessments and mitigation strategies.  

Design Principles:  
1. Implement a strong identity foundation  
  - Stick to the principle of least privilege, and enforce seperation of duties.  
  - Use the appropriate authorization for each interaction with your AWS resources.  
  - Centralize privilege management and reduce or even eliminate reliance aon long-term credentials.  
2. Enable traceability  
  - Monitor, alert, and audit actions and changes to your environment in real time.  
  - Integrate logs and metrics with systems to automatically respond and take action.   
3. Apply security at all layers  
  - Rather than just focusing on protecting a single outer layer, apply a defense-in-depth approach with other security controls  
  - Apply to all layers, for example, edge network, vritual private cloud(VPC), subnet, load balancer, every instance, operating system, and application  
4. Automate security best practices  
  - Automation improves your ability to securely scale more rapidly and cost effectively  
  - Create secure architectures, including the implementation of controls that are defined and managed as code  
5. Protect data in transit and rest  
  - Classify your data into sensitivity levels and use mechanisms, such as encryption and tokenization where appropriate  
  - Reduce and eliminate direct human access to data to reduce risk of loss or modification  
6. Prepare for security events  
  - Institute an incident management process  
  - Run incident response simulations and use rools with automation to increase your speed for detection, investigation, and recovery  
  
##### Reliability Pillar  
The reliability pillar includes   
- the ability of a system to recover from infrastructure or service disruptions  
- dynamically acquire computing resources to meet demand  
- Mitigate disruptions  

Design Principles  
1. Test recovery procedures  
- In an on-premises environment, testing is often conducted to prove the system works in a particular scenario  
- Testing is not typically used to validate recovery strategies   
- In the cloud, you can test how your system fails, and you can validate your recovery procedures  
- You can use automation to simulate different failures or to recreate scenarios that led to failures before  
- This exposes failure pathways that you can test and rectify before a real failure scenario, reducing the risk of components failing that have not been tested before  

2. Automatically recover from failure  
- By monitoring a system for key performance indicators(KPIs), you can trigger automation when a threshold is breached  
- This allows for automatic notification and tracking of failures, and for automated recovery processes that workaround or repair the failure  
- With more sophisticated automation, it's possible to anticipate and remediate failures before they occur   

3. Scale horizontally to increase aggregate system availability  
- Replace one large resource with multiple small resources to reduce the impact of a single failure on the overall system  
- Distribute requests across multiple, smaller resources to ensure that they don't share a common point of failure  

4. Stop guessing capacity  
- A common cause of failure in on-premises systems is resource saturation, when the demands placed on a system exceed the capacity of that system(including denial of service attacks).  
- In the cloud, you can monitor demand and system utilization, and automate the addition or removal of resources to maintain the optimal level to satisfy demand  

5. Manage change in automation  
- Changes to your infrastructure should be done using automation  
- The changes that need to be managed are changes to the automation configuration  

##### Performace Efficiency Pillar
The Performance efficiency pillar includes:
1. the ability to use computing resources efficiently to meet system requirements
2. the ability to maintain that efficiency as demand changes and technologies evolve  

Design principles:  
1. Democratize advanced technologies  
- Some complex technologies require expertise that is not evenly dispersed across the technical community. For example, NoSQL databases, media transcoding, and machine learning.  
- In the cloud, these technologies can become services that your team can consume while focusing on product development rather than resource provisioning and management,  

2. Go global in minutes  
- Easily deploy your system in multiple Regions around the world with just a few clicks.  
- This allows you to provide lower latency and a better experience for your customers at minimal cost.  

3. Use serverless architectures  
- In the cloud, serverless architectures remove the need for you to run and maintain servers to carry out traditional compute activities.  
- For example, storage services can act as static websites, removing the need for web servers, and event services can host your code for you.  
- This not only removes the operational burden of managing these servers, but also can lower transactional costs because these managed services operate at cloud scale.  

4. Experiment more often  
- With virtual and automatable resources, you can quickly carry out comparative testing using different types of instances, storage, or configurations.  

5. Mechanical sympathy  
- Use the technology approach that aligns best to what you are trying to achieve.  
- For example, consider data access patterns when selecting database or storage approaches.  

##### Cost Optimization Pillar  
The cost optimization pillar includes the ability to avoid or eliminate unneeded cost or suboptimal resources.  

Design Principles：  
1. Adopt a consumption model  
- Pay only for the computing resources that you consume and increase or decrease usage depending on business requirements, not by using elaborate forecasting.  
- For example, development and test environments are typically only used for 8 hours a day during the work week. You can stop these resources when they are not in use for a potential cost savings of 75%.(40 hours vs 168 hours)    

2. Measure overall efficiency  
- Measure the business output of the system and the costs associated with delivering it. Use this measure to understand the gains you make from increasing output and reducing costs.  

3. Stop spending money on data center operations  
- AWS does the heavy lifting of racking, stacking, and powering servers, so you can focus on your customers and business projects rather than on IT infrastructure.  

4. Analyze and attribute expenditure  
- The cloud makes it easier to accurately identify the usage and cost of systems, which then allows attribution of IT costs to the various business owners.  
- This helps measure return on investment and gives system owners an opportunity to optimize their resources and reduce costs.  

5. Use managed services to reduce cost of ownership    
- In the cloud, managed services remove the operational burden of maintaining servers for tasks like sending email or managing databases.  
- And because managed services operate at cloud scale, they can offer a lower cost per transaction or service.  


### Fault Tolerance and High Availability  
- Fault Tolerance  
	- the ability for a system to remian operational even if some of the componenets of that system fail.   
	- It can be seen as the built-in redundancy of an application's components.     
- High availability  
	- is a concept regarding the entire system.    
	- Its goal is to ensure that your systems are always functioning and accessible, and that downtime is minimized as much as possible, without the need for human intervention.    
	- Even if a site is unavailable for a single minute, it can be crippling to a business.  

Amazon Web Services provides tools to assist in these times of need.  
- Build fault-tolerant, highly available systems  
- Minimal human interaction  
- Minimal up-front financial investment   


#### On Premise VS AWS
- Traditional(Ensuring high availability)  
	- Very expensive  
	- Only mission-critical applications    
- AWS(Have options to expand availability and recoverability amongst whatever servers you choose)  
	- Multiple servers  
	- Availability Zones(AZ's)  
	- Multiple Regions  
	- Fault-tolerance seervices   
	
#### Some specific services can assist in ensuring high availability  
- Elastic Load Balancers(ELB)  
- Elastic IP address   
- Amazon Route 53   
- Auto Scaling  
- Amazon CloudWatch  


##### Elastic Load Balancers  
- ELBs is a service that distributes incoming traffic or loads amongst your instances.  
- ELB can also send metrics to Amazon CloudWatch, which is a managed monitoring service.  
- ELB can be a trigger and notify you of high latency or if servers are becoming over-utilized.  
- ELB can also be customized. For example, you can configure it to recongnize unhealthy or specific metrics on your instance. It can be public or internal-facing. It can use multiple different protocols.   

##### Elastic IP addresses  
- Elastic IP addresses are useful in providing greater fault-tolerance for your application.   
- Elastic IPs are static IP addresses designed for dynamic cloud computing. This tool allows you to mask a failure of an instance or software by allowing your users to use the same IP addresses with replacement resources.  
- Using Elastic IP addresses ensures high availability because your clients can still access your application even if your instance were to fail.   

##### Amazon Route 53  
- Amazon Route 53 is an authoritative DNS service from AWS.    
- This is used to translate domain names into IP addresses.   
- Amazon Route 53 is designed and maintained with the highest level of availability in mind.  
- It was developed to support simple outing, latency-based routing, health checks and DNS failovers, and geolocation routing.  
- All of these characteristics increase the availability of your customer-facing applications.  

##### Auto Scaling  
- Auto Scaling launches or terminates instances based on specified conditions.  
- This service is designed to assist you in building a flexible system that can adjust and be modified depending on changes in customer demand.  
- With auto scaling, you can avoid limitations of being able to create new resources. Instead, you can create new resources on demand or have scheduled provisioning.  
- This ensures that your applications and systems are always available no matter what the load is.  
- You can set provisions to scale up or down, depending on your policies.  

##### Amazon CloudWatch
- Amazon CloudWatch is a distributed statistics-gathering system.  
- It collects and tracks your metrics of your applications.  
- You have the ability to create and use your own custom metrics.  
- If there is high latency or metrics that have passes the set threshold, CloudWatch can adjust automatically to ensure high availability of your architecture.     

#### Some fault-tolerant tools    
- Amazon Simple Queue Service(Amazon SQS)  
- Amazon Simple Storage Service(Amazon S3)  
- Amazon SimpleDB  
- Amazon Relational Database Service  

##### Amazon Simple Queue Service(Amazon SQS)  
- It can be used as the backbone of your fault-tolerant application.    
- It is a highly reliable distributed messaging system.  
- Amazon SQS can help you ensure that your queue is always available.   


##### Amazon Simple Storage Service(Amazon S3)  
- It provides hihg durability and fault-tolerant data storage.  
- It is a simple web service that you can utilize and only pay for the storage your use.  
- Amazon S3 stores all of your data redundantly on multiple different devices across multiple facilities in a region, so if there was ever a failure, you will still have access to all of your information.  

##### Amazon SimpleDB  
- It is fault-tolerant and durable structured data storage solution.  
- By using SimpleDB, you have full advantage to a scalable service and can avoid single points of failure due to its natural design for high availability and fault tolerance.  

##### Amazon Relational Database Service(Amazon RDS)    
- It is another web service tool to use in regards to relational databases.  
- It provides high availability and fault tolerance by offering several features to enhance the reliability of your critical databases.   
- Some of these features include automated backups, snapshots, and multi-Availability Zone deployments. 


All of these different services are highly reliable, highly durable, and fault-tolerant tools for your applications to ensure high availability and fault-tolerant systems.  


