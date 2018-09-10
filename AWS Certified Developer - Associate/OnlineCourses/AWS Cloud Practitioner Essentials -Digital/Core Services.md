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








