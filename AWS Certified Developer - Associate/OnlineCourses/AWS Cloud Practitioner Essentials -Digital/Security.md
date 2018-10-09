## AWS Cloud Practitioner Essentials: Security

### Conents
* [Introduction to AWS Security](#introduction-to-aws-sercurity)  
* [The AWS Shared Responsibility Model](#the-aws-shared-responsibility-model)  
* [AWS Access Control and Management](#aws-access-control-and-management)
* [AWS Security Compliance Programs](#aws-security-compliance-programs)

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


### AWS Access Control and Management  
AWS Identity and Access Management, or IAM, is a web service that helps you:  
- Securely control access to AWS resoucers for you and your users.  
- Authentication  
  - Who can access resources  
- Authorization  
  - How they can use resources  
- Compute  
- Storage  
- Database  
- Application services  

##### Access Control Concepts  
User, Group, Permissions, Role  
- Create users and groups  
- Use permissions  

#### IAM functionality  
- Manage IAM users and their access  
- Manage IAM roles and their permissions  
- Manage federated users and their permissions  

#### AWS Account Root User  
AWS Account Root User: first create an AWS account, you begin with a single sign-in identity that has complete access to all AWS services and resources in the account. 
Recommendations:  
- Delete root user access keys  
- Create an IAM user  
- Grant administrator access  
- Use those credentials  

#### AWS Authentication  
When adding users, you got to select how users will access AWS. There are two different types of access you can assign users:  
1. Programmatic access  
2. AWS Management Console access  

##### Programmatic accesss 
- Enables access key ID and secret access key  
- For AWS API, CLI, SDK, and other development tools  

##### Management Console access  
- Sign-in to the AWS Management Console  
- Uses AWS account name and password  
- MFA(Multi-Factor Authentication) prompts for code  

#### IAM Authorization  
- After a user has been authenticated, they then have to be authorized to be able to access an AWS service.  
- AWS IAM Policy  
  - which is a document that explicitly lists permissions  
  - One policy can be assigned to an IAM User, IAM Group, and IAM Roles  
  
#### Demonstration  
Login to the AWS Mangement Console, create a user, assign the user to a group and apply permissions  

Sercurity, Identity & Compliance -> IAM

### AWS Security Compliance Programs  
AWS does communicate its security and control environment relevant to customers. AWS does this by doing the following:  
- Obtaining industry certifications and independent third-party attestation.  
- Publishing information about the AWS security and control practices in whitepapers and web site content.  
- Providing certificates, reports, and other documentation directly to AWS customers under NDA as requird.  

#### Assurance Programs  
- Certifications/Attestations  
- Laws, Regulation, and Privacy  
- Alignments/Frameworks  

#### AWS Risk and Compliance Programs  
- Information about AWS controls  
- Assist customers in documenting their framework  

The AWS Risk and Compliance Program is made up of three components:  
- Risk management  
- Control environment  
- Information security  

##### Risk management  
- Strategic business plan includes risk management  
- Re-evaluated at least biannually  
- Identify risks  
- Implement appropriate measures  
- Additional internal/external risk assessments  

The AWS Compliance and Security teams have established an information security framework and policies based on the following governing bodies:  
- COBIT  
  - Control Objectives for Information and related Technology  
- AICPA  
  - American Institute of Certified Public Accountants  
- NIST  
  - National Institute of Standards and Technology   
  
- AWS maintains the security policy  
- Provides security training to employees  
- Performs application security reviews  
  - Confidentiality  
  - Integrity 
  - Availability of data  
  - Conformance to IS policy  
- Scan service endpoints for vulnerabilities  
- Notifies for remediation of vulnerabilities  
- Assessment by Independent security firms  
- Not a replacement for customer scans  
- Customers can request to scan cloud infrastructure  
  - Limited to their instances  
  - Within AWS Accepatable Use Policy  
  
##### Control Environment  
- Includes policies, processes, control activities  
- Secure delivery of AWS's service offerings  
- Supports the operating effectiveness of AWS's control framework  
- Integrates controls by leading cloud computing industry bodies  
- AWS monitors for leading practices  

##### Information Security  
- Designed to protect  
  - Confidentiality  
  - Integrity  
  - Availability   
- Security whitepaper  

##### Customer Compliance  
- Governance over the entire IT control environment  
- Understanding of required compliance objectives  
- Establishment of a control environment  
- Validation based risk tolerance  
- Verification of effectiveness  

Strong customer compliance and goverance might include the following basic approach:  
- Review  
  - Review information available from AWS together with other information to understand as much as of the entire IT environment as possible, and then document all compliance requirements   
- Design  
  - Design and implement control objectives to meet the enterprise compliance requirements   
- Identify   
  - Idnetify and documnent controls owned by outside parties  
- Verify  
  - Verify that all control objectives are met and all key controls are designed and operating effectively  
  







  

