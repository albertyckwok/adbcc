# Oracle Autonomous Database on Exadata Cloud@Customer
Please visit https://osc.oraclecorp.com/ to submit an engagement request if you want to engage us for this workshop or other activities(Demo, PoC, etc). [Click to see further instruction](labs/oscRequest.md).

## Introduction
Oracle Autonomous Database (ADB) on Exadata Cloud@Customer (ExaCC) combines the benefits of a self-driving, self-securing, and self-repairing database management system and the security and control offered by having it deployed securely on premise behind your firewall. 

## Workshop topics
This is a series of hands-on labs designed to familiarize participants with all major features and functions of ADB on ExaDB. Most of the topics/lessons can be delivered independently so that the workshop agenda can be customized based on the needs and interest of the customers.

[Lesson 1: Introduction to ADB on ExaCC](lessons/intro2adbCC.md).

- Practices for Lesson 1:
  1. [Cloud/OCI control plane](labs/accessOCI.md)
  1. [Access Cloud Resource](labs/access.md)
  1. [Basic setup and navigation for labs](labs/setupNavBasics.md)

[Lesson 2: Database Life Cycle](lessons/basicOperation.md).

- Practices for Lesson 2:

  1. [Create Database](labs/createDB.md)
  3. [Work Requests](../ecc/labs/workRequests.md)
  1. [Scaling and Performance Monitoring](labs/adb-scaling.md)
  4. [Clone an Autonomous Database](labs/cloneDB.md)
  5. [Terminate an Autonomous Database](labs/deleteDB.md)

[Lesson 3: Identity and Access Management](../ecc/lessons/identityAndAccessManagement.md).

- Practices for Lesson 3:

  1. [IAM Practice - Identity and Access Management](labs/adbIAM.md)
  1. [Multi-Factor Authentication (MFA)](labs/mfaIAM.md)
  2. [OCI Audit Service](../ecc/labs/audit-service.md)

[Lesson 4: Security](../ecc/lessons/dbSecurity.md).

- Practices for Lesson 4:

  1. [Transparent Data Encryption (TDE)](labs/tde.md)
  2. [Database Network Encryption](labs/dbNetEnc.md)
  3. [Database Vault](labs/DBVault.md)

[Lesson 5: Developer/DevOps Tools and Methodology](../ecc/lessons/devOpsToolsAndMethodology.md).

- Practices for Lesson 5:

  1. [OCI CLI](labs/OCI-CLI.md)
  1. [Getting started with GitHub](labs/gitBeginner.md)
     - [Install VS Code IDE (optional)](../ecc/labs/vsCode.md)
  2. [Getting started with Terraform](../ecc/labs/tfBeginner.md)
  3. [Manage database with Terraform](labs/tf4Db.md)
  3. [IaC with OCI Resource Manager(ORM)](../ecc/labs/orm.md)
  3. [SQL Developer Web and RESTful Services](labs/adb-sqldevweb.md)
  1. [Oracle Application Express (APEX)](labs/Apex.md)


[Lesson 6: MAA/ADG - HA, data protection and DR](../ecc/lessons/dbMAA.md).

- Practices for Lesson 6:

  1. [Data Guard (WIP)](https://docs.oracle.com/en-us/iaas/exadata/doc/adb-using-adg-with-adb.html)
  2. [Backup and Recovery](labs/backupRestore.md)

[Lesson 7: Enterprise Manager and Cost Management](../ecc/lessons/enterpriseManager.md).

- Practices for Lesson 7:


  1. [Enterprise Manager](labs/emAdb.md)
  1. [EM Chargeback (WIP)](../ecc/labs/emCrossCharge.md)
  1. [Cost and Usage (WIP)](https://github.com/oracle/oci-python-sdk/tree/master/examples/usage_reports_to_adw)

Lesson 8: Administration and Maintenance

- Practices for Lesson 8:

  1. [Manage Autonomous Container Database](labs/ProvisionACD.md)
  2. [Terminate an Autonomous Container Database](https://docs.cloud.oracle.com/en-us/iaas/exadata/doc/eccmanagingacds.html#GUID-7944B79E-9631-4F3F-A135-9C0DC4FAD5B3)

Lesson 9: Provisioning Exadata Cloud@Customer Systems

- Practices for Lesson 9:

  1. [Create ExaCC Infrastructure](https://docs.cloud.oracle.com/en-us/iaas/exadata/doc/eccprovisioning.html#GUID-BE985DBA-C568-4915-8A09-57893B541D9D)
  2. [Create a VM Cluster Network](https://docs.cloud.oracle.com/en-us/iaas/exadata/doc/eccmanagingvmclusters.html#GUID-C1F49BDB-1249-4AE7-9ECB-7AEC406F05ED)
  3. [Validate a VM Cluster Network](https://docs.cloud.oracle.com/en-us/iaas/exadata/doc/eccmanagingvmclusters.html#GUID-2864625D-8FDD-4DBF-A6AF-499111FE281A)
  4. [Edit a VM Cluster Network](https://docs.cloud.oracle.com/en-us/iaas/exadata/doc/eccmanagingvmclusters.html#GUID-0BC2881E-8B56-4432-B24A-959A090800D8)
  5. [Create a VM Cluster](https://docs.cloud.oracle.com/en-us/iaas/exadata/doc/eccmanagingvmclusters.html#GUID-9A45C3AD-6453-4173-812B-5EF94D9CA876)
  6. [Managing Backup Destinations](https://docs.cloud.oracle.com/en-us/iaas/exadata/doc/eccmanagingbackupdest.html)

[Lesson 10: Exadata Features and Functions](../ecc/lessons/dbFeaturesCapabilities.md).

- Practices for Lesson 10:

  1. [Smart Scan](../ecc/labs/smartScan.md)
  2. [Advanced Compression](../ecc/labs/hcc.md)
