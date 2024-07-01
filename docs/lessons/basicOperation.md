# Slide 1: ExaCC Autonomous Database - Technical Deep Dive
![slide01.jpg](basicOperation.images/slide01.jpg)


Think of OSC is the showcase in a car dealership where potential car buyer will go and test drive before they buy. OSC offer similar service such as:
1. Demo - take the customer for a ride on a brand new car to show different features.
2. Workshop - teach the customer how to drive before handing the key to allow customer to test drive themselves.
3. PoC (Proof of Concept) - hand the key to the customer for them to test drive themselves.

Oracle Sales can submit activity request at https://osc.oraclecorp.com/. Customer can view https://www.oracle.com/osc/ page for more details.


# Slide 2
![slide02.jpg](basicOperation.images/slide02.jpg)


I am required to let you read the Safe harbor statement for a few seconds.


# Slide 3: How does Multi-VM Autonomous Database Work?
![slide03.jpg](basicOperation.images/slide03.jpg)




# Slide 4: How does Multi-VM Autonomous Database Work?
![slide04.jpg](basicOperation.images/slide04.jpg)




# Slide 5: Autonomous Database - Dedicated Consolidation Constraints
![slide05.jpg](basicOperation.images/slide05.jpg)


This is a bit of eye chart, you can read the details. The main thing here is that if you want to have the max ACD counts, then you need 2 AVM for Exa M machine that will give your 24 and 30 respectively for X8M and X9M


# Slide 6: Multiple VM Autonomous Database for Cloud@Customer
![slide06.jpg](basicOperation.images/slide06.jpg)




# Slide 7
![slide07.jpg](basicOperation.images/slide07.jpg)




# Slide 8: Gen 2 Exadata Cloud@Customer Architecture Overview
![slide08.jpg](basicOperation.images/slide08.jpg)


1. CPS requires no inbound TCP connections
2. CPS requires outbound access on TCP/443 to OCI
3. Passive proxy (e.g., corporate proxy) supported
   * Challenge proxy and traffic inspection are not supported
   * Oracle does not provide a mechanism for customer certificate management of TLS VPN.  A passive (no inspection) proxy can be implemented.


The gen 2 network block diagram depicts the networking between the major subsystems that make up an Exadata Cloud at Customer deployment.  

The Exadata Cloud at Customer deployment on the left is located in the data center of the customer's choice.  The infrastructure components are owned and managed by Oracle.  The gen 2 control plane, hosted in an OCI region, executes Cloud Automation functionality on behalf of the customer by sending commands to the local Control Plane Servers deployed in the Exadata Cloud at Customer rack. There are 3 types of access:
1. Infrastructure access by Oracle staff (red arrow)
2. Infrastructure access by Oracle Cloud automation (red arrow)
3. Customer database and DomU access by Oracle Cloud automation (blue arrow)
4. 
Oracle staff accesses Exadata Cloud at Customer infrastructure via bastion servers and the gen 2 control plane as follows
1. Oracle cloud ops staff logs into bastion server as a named user via 2FA using a hardware UbiKey
2. Oracle cloud ops staff accesses the local control plane server as named user via an ssh proxy configured in the gen 2 control plane
3. Oracle cloud ops staff accesses infrastructure components via ssh as a privileged user
4. 
Oracle Cloud Automation accesses  Infrastructure (Dom0), 

Customer's consume DomU and database resources via layer 2 connections to customer managed switches, shown in shades of blue. 




# Slide 9
![slide09.jpg](basicOperation.images/slide09.jpg)




# Slide 10
![slide10.jpg](basicOperation.images/slide10.jpg)




# Slide 11
![slide11.jpg](basicOperation.images/slide11.jpg)




# Slide 12
![slide12.jpg](basicOperation.images/slide12.jpg)




# Slide 13
![slide13.jpg](basicOperation.images/slide13.jpg)




# Slide 14
![slide14.jpg](basicOperation.images/slide14.jpg)




# Slide 15
![slide15.jpg](basicOperation.images/slide15.jpg)




# Slide 16
![slide16.jpg](basicOperation.images/slide16.jpg)




# Slide 17
![slide17.jpg](basicOperation.images/slide17.jpg)




# Slide 18
![slide18.jpg](basicOperation.images/slide18.jpg)




# Slide 19
![slide19.jpg](basicOperation.images/slide19.jpg)




# Slide 20
![slide20.jpg](basicOperation.images/slide20.jpg)




# Slide 21
![slide21.jpg](basicOperation.images/slide21.jpg)




# Slide 22
![slide22.jpg](basicOperation.images/slide22.jpg)




# Slide 23
![slide23.jpg](basicOperation.images/slide23.jpg)




# Slide 24
![slide24.jpg](basicOperation.images/slide24.jpg)




# Slide 25
![slide25.jpg](basicOperation.images/slide25.jpg)




# Slide 26
![slide26.jpg](basicOperation.images/slide26.jpg)




# Slide 27
![slide27.jpg](basicOperation.images/slide27.jpg)




# Slide 28
![slide28.jpg](basicOperation.images/slide28.jpg)




# Slide 29
![slide29.jpg](basicOperation.images/slide29.jpg)




# Slide 30
![slide30.jpg](basicOperation.images/slide30.jpg)




# Slide 31
![slide31.jpg](basicOperation.images/slide31.jpg)




# Slide 32
![slide32.jpg](basicOperation.images/slide32.jpg)




# Slide 33
![slide33.jpg](basicOperation.images/slide33.jpg)




# Slide 34
![slide34.jpg](basicOperation.images/slide34.jpg)


Database Backup Options with ExaCC:

* Using Cloud Automation
   Oracle Public Cloud Object Storage
   Object Storage and Local Exadata Storage (FRA)
   Zero Data Loss Recovery Appliance
   Local NFS-attached storage
* Manual configuration to existing on-premises backup infrastructure
   Customer must install backup agents in DomU and configure RMAN

ZDLRA is the best for backup ExaCC database. ZDLRA's virtual full backups using Incremental Forever Architecture has the best performance and space efficiency. It takes the redo logs from the database similar to dataguard that has minimal performance impact on the database. ZDLRA allows customer to send backup to the cloud archive storage for long term retention so you get the best of both worlds. Archive storage is 1/10 of the cost of active object storage and it is perfect solution to replace traditional tape backup for long term retention. In additional, you can replicate backup in object storage to another regions. OCI typically has 2 regions per country that is far enough apart, typically on opposite site of the country. For example, in the USA, the west cost region in Phoenix AZ is more than 2,000 miles from the east cost region Ashburn, so your backup will be saved even if half of the country got destroyed by tsunami from pacific ocean or meteoroid strikes the Atlantic ocean.


# Slide 35: Recovery Appliance Recommended
![slide35.jpg](basicOperation.images/slide35.jpg)




# Slide 36
![slide36.jpg](basicOperation.images/slide36.jpg)




# Slide 37: Labs
![slide37.jpg](basicOperation.images/slide37.jpg)




# Slide 38: Labs
![slide38.jpg](basicOperation.images/slide38.jpg)




# Slide 39
![slide39.jpg](basicOperation.images/slide39.jpg)




