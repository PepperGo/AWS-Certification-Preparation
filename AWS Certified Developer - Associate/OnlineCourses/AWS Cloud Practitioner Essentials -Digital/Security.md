## AWS Cloud Practitioner Essentials: Security

### Conents
* [Introduction to AWS Security](#introduction-to-aws-sercurity)  
* [The AWS Shared Responsibility Model](#the-aws-shared-responsibility-model)  


### Introduction to AWS Security
##### Keep your data safe
- Resilient infrastructure  
- High security  
- Strong Safeguards  

##### Continual Improvement  
- Rapid innovation  
- Constantly evolving security services  

##### Pay for what you need  
- Meet needs at lower operational costs  

##### Meet Compliance Requirements  
- Governance-enabled features  

##### AWS Shared Responsibility Model  
- Inherit AWS security controls  
- Layer your controls  

##### Security Products and Features  
- Tools from AWS and partners  
- Monitoring and logging  

##### Network Security  
- Built-in firewalls  
- Encryption in transit  
- Private/dedicated connections  
- DDOS mitigation

##### Inventory and Configuration Management  
- Manage creation/decommissioning of AWS resources  
- Inventory and configuration tools  
- Template definition and tools  

##### Data Encryption  
- Encryption capabilites for AWS storage/database services  
- Key management options  
- Hardware-based cryptographic key storage options  

##### Access Control and Management  
- Identity and access management(IAM)  
- Multifactor authentication   
- Integration and federation with corporate directories  

##### Monitoring and Logging  
- Deep visibility into API calls  
- Log aggregation and options  
- Alert notification  
- Reduce your risk profile  

##### AWS Marketplace  
- Partner security porducts  
- Complement AWS features and tools  

### The AWS Shared Responsibility Model  
#### Under the cloud
Under the shared responsibility model, AWS operates, manages, and controls the components from the host operating system and virtualization layer down to the physical security of the facilities in which the services operate.  
It means that AWS is reponsible for protecting the global infrastructure that runs all of the services offered in the AWS cloud which include Regions, Availability Zones and Edge Locations.  
For all the services, AWS will handle basic security tasks like guest operating system(OS) and database patching, firewall configuration, and disaster recovery.  

#### In the Cloud  
While the cloud infrastructure is secured and maintained by AWS, customers are responsible for security of everything they put in the cloud.  
customers maintain complete control over their content and are responsible for managing critical content security requirements, including:  
- What to store  
- Which AWS services  
- In what location  
- Content format and structure  
- Who has access to that content  
- Access rights  

Customers can use AWS Service catalog to create and manage catalogs of IT services that have been approved for use on AWS.  
AWS products that fall into the category of laaS, such as Amazon EC2, and Amazon VPC, are completely under the customer's control which requires them to perform all of the necessary sercurity configuration and management tasks.  






