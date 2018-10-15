## AWS Cloud Practitioner Essentials: Architecting   

### Conents
* [Introduction to the Well Architected Framework](#introduction-to-the-well-architected-framework)  

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
  
##### 
 





























