# Transparent Data Encryption (TDE)
## Introduction
As mention in the lesson Transparent Data Encryption (TDE) which encrypts data "at rest" is enable and included for ExaCC out-of-box. ExaCC automatically encrypt all tablespaces. Encrypted data is transparently decrypted for a database user or application that has access to data. TDE helps protect data stored on media in the event that the storage media or data file is stolen. To prevent unauthorized decryption, TDE stores the encryption keys in a security module external to the database.

### How does TDE work?

TDE is a key-based access control system. Even if the encrypted data is retrieved, it is useless without authorized decryption, which occurs automatically for users authorized to access the table.

The following show how TDE work:

1. It retrieves the master key from the wallet.
2. It decrypts the encryption key for that table from the data dictionary.
3. It uses that encryption key on the input value.
4. It stores the encrypted data in the database.
![TDEworkflow](https://docs.oracle.com/database/121/ASOAG/img/GUID-5FD3A3BB-441C-4C42-A520-1248974627B0-default.png)

## Required Artifacts

This lab requires the artifact describe in [commPreReq.md, click to see or right mouse button click to open new tab as you may need it for other labs](../ecc/labs/commPreReq.md).

## **Tasks**

### **Task 1**: Get connection string to database

1.  Open the navigation menu. Under **Database**, click **Exadata Cloud@Customer**.
    ![eccMenu.png](images/eccMenu.png)
2.  Click **Autonomous Databases**.
    - You may need to select the compartment that you are assigned to if it is not selected already.
3. Click the Name of your database. 
5. In Database details window, click the **DB Connection** button, select Copy on one of the connection string, e.g. _medium, then paste to set the cs variable in the command shell.
    ![atpCS](images/atpCS.png)
5. On the terminal windows, run the SQL connect to the newly created database and see what table spaces are created.
   ```
   cs=
   sqlplus "ADMIN/${myPwd}@$cs"
   select * from global_name;
   select * from V$TABLESPACE;
   ```

### **Task 2**: TDE tablespace encryption
1. Display the encryption setting for the PDB.
   ```sql
   column WRL_PARAMETER format A15
   column status format A8
   SELECT con_id, WRL_PARAMETER, KEYSTORE_MODE, status FROM v$encryption_wallet;
   ```
    - KEYSTORE_MODE is UNITED indicating that PDB is configured to use the wallet of the CDB$ROOT.
    - Similarly WRL_PARAMETER is empty because it is on the CDB.
4. Show details of what tablespaces are encrypted and how or what algorithm was been used to encrypt data.
   ```sql
   select * from V$TABLESPACE;
   select TS#, ENCRYPTIONALG, ENCRYPTEDTS, CON_ID from V$ENCRYPTED_TABLESPACES;
   ```
    - All tablespaces are encrypted with AES128.
    - AES stands for Advanced Encryption System.  It is an encryption algorithm used in IT applications to secure sensitive materials. AES was selected in 2001 as an official government security standard, but over time it also became the de facto encryption standard for the private sector.  The AES security standard can be applied to restrict access to both hardware and software. [The EE Times points out](http://www.eetimes.com/document.asp?doc_id=1279619) that even using a supercomputer, a "brute force" attack would take one billion years to crack AES 128-bit encryption.
5. Exit from the PDB (ctrl-D).
   ```
   exit
   ```

The following is a sample input and output:

```
akwok@devtool3:~ $ pp=BEstr0ng###;myInit=xx;myDBnum=0
akwok@devtool3:~ $ cs='(DESCRIPTION=(CONNECT_TIMEOUT=120)(RETRY_COUNT=20)(RETRY_DELAY=3)(TRANSPORT_CONNECT_TIMEOUT=3)(ADDRESS_LIST=(LOAD_BALANCE=on)(ADDRESS=(PROTOCOL=TCP)(HOST=exacc4-01-scan.us.osc.oracle.com)(PORT=1521)))(CONNECT_DATA=(SERVICE_NAME=XXPDB0C_medium.atp.oraclecloud.com)))'
akwok@devtool3:~ $ sqlplus "ADMIN/${myPwd}@$cs"

SQL*Plus: Release 19.0.0.0.0 - Production on Tue Sep 1 14:19:41 2020
Version 19.6.0.0.0

Copyright (c) 1982, 2019, Oracle.  All rights reserved.

Last Successful login time: Tue Sep 01 2020 11:13:46 -07:00

Connected to:
Oracle Database 19c EE Extreme Perf Release 19.0.0.0.0 - Production
Version 19.8.0.0.0

SQL> select * from global_name;

GLOBAL_NAME
--------------------------------------------------------------------------------
XXPDB0C.ATP.ORACLECLOUD.COM

SQL> column WRL_PARAMETER format A15
column status format A8
SELECT con_id, WRL_PARAMETER, KEYSTORE_MODE, status FROM v$encryption_wallet;
SQL> SQL> 
    CON_ID WRL_PARAMETER   KEYSTORE STATUS
---------- --------------- -------- --------
         5                 UNITED   OPEN

SQL> select * from V$TABLESPACE;

       TS# NAME                           INC BIG FLA ENC     CON_ID
---------- ------------------------------ --- --- --- --- ----------
         0 SYSTEM                         YES YES YES              5
         1 SYSAUX                         YES YES YES              5
         2 UNDOTBS1                       YES YES YES              5
         4 UNDO                           YES YES YES              5
         6 UNDO_4                         YES YES YES              5
         7 UNDO_5                         YES YES YES              5
         8 DATA                           YES YES YES              5
         9 TEMP                           NO  YES YES              5
        10 DBFS_TS                        YES YES YES              5

9 rows selected.

SQL> select TS#, ENCRYPTIONALG, ENCRYPTEDTS, CON_ID from V$ENCRYPTED_TABLESPACES;

       TS# ENCRYPT ENC     CON_ID
---------- ------- --- ----------
         0 AES128  YES          5
         1 AES128  YES          5
         2 AES128  YES          5
         4 AES128  YES          5
         6 AES128  YES          5
         7 AES128  YES          5
         8 AES128  YES          5
        10 AES128  YES          5
         9 AES128  YES          5

9 rows selected.

SQL> Disconnected from Oracle Database 19c EE Extreme Perf Release 19.0.0.0.0 - Production
Version 19.8.0.0.0

```

### Conclusion ###
Out-of-Box TDE feature of ExaCC secures data from unauthorized, or back-door, access. TDE encrypts data at rest to stop database bypass attacks from accessing sensitive information in storage. TDE provides data encryption and compliance with no coding and key management complexity. Thus, it enables you to focus on more strategic efforts.

## References ##

- [Introduction to Transparent Data Encryption](https://docs.oracle.com/database/121/ASOAG/introduction-to-transparent-data-encryption.htm#ASOAG10117)
- [Master Note For Transparent Data Encryption ( TDE ) (Doc ID 1228046.1)](https://support.oracle.com/epmos/faces/DocumentDisplay?id=1228046.1)