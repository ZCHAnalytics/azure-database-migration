# Setting up production environment

## 1.  Provision a Windows Virtual Machine
In order to emulate the functionalities of a Windows server and replicate the operations of an on-premise system within a company, a Windows Virtual Machine (VM) will be set up. This VM will act as a secure and dedicated data storage solution, serving as a repository for the company's database throughout the project:
<img alt="Provisioning a Virtual Machine" width="1000" src="https://github.com/ZCHAnalytics/azure-database-migration319/assets/146954022/ebb07f9b-e09d-4c29-a279-01f16953c154">

## 2.  Secure connection to the VM:
Ensuring secure communication with the VM by configuring the appropriate network settings and firewall rules:
<img alt="Securing connection to VM" width="1000" src="https://github.com/ZCHAnalytics/azure-database-migration319/assets/146954022/7f102506-2b71-49bc-8935-73252a39bd5a">

## 3.  Install SQL Server and SSMS:
SQL Server and SQL Server Management Studio tools are essential for database management within the production environment, mirroring the corporate database server capabilities. 
<p float="left">
  <img alt="installing SQL Server" src="https://github.com/ZCHAnalytics/azure-database-migration319/assets/146954022/9fdd2ca0-a20d-47b1-9b0f-14930d4af5b3" width="500" />
  <img alt="Installing SSMS" src="https://github.com/ZCHAnalytics/azure-database-migration319/assets/146954022/904e8d82-a30d-4b3e-a6df-0b8fc3294b0f?" width="500" /> 
</p>

## 4.  Create Production Database
Create the production database by restoring it from a backup file. This database is an illustrative and comprehensive sample database that emulates a fictional manufacturing company's operations. It encompasses various tables, views, stored procedures, and data, offering a rich and diverse dataset.

### 4.1.  Create a backup file in the SSMS backup folder: 
<img alt="Create backup file in SSMS" width="1000" src="https://github.com/ZCHAnalytics/azure-database-migration319/assets/146954022/398ae6e4-52f9-4408-a78f-272f9e08e38a">

### 4.2.  Restore database from backup:
<img alt="Restoring the database from backup" width="1000" src="https://github.com/ZCHAnalytics/azure-database-migration319/assets/146954022/47636c0b-6e6b-41f4-a4fb-456e8a81a077">

### 4.3.  Test if data is present: 
<img alt="Testing if database if functional" width="1000" src="https://github.com/ZCHAnalytics/azure-database-migration319/assets/146954022/4d488651-436d-4685-b4a5-dfd73fc7b25f">
