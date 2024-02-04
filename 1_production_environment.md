# Setting up production environment

## Establishing a Windows Virtual Machine
In order to emulate the functionalities of a Windows server and replicate the operations of an on-premise system within a company, a Windows Virtual Machine (VM) will be set up. This VM will serve as a secure and dedicated data storage solution, acting as a repository for the company's database throughout the project:
<img width="1000" src="https://github.com/ZCHAnalytics/azure-database-migration319/assets/146954022/ebb07f9b-e09d-4c29-a279-01f16953c154">

## Connecting to the VM using appropriate network settings and firewall rules:
Ensuring secure communication with the VM with the appropriate network settings and firewall rules:
<img width="1000" src="https://github.com/ZCHAnalytics/azure-database-migration319/assets/146954022/7f102506-2b71-49bc-8935-73252a39bd5a">

## Install SQL Server and SSMS on Virtual Machine:
SQL Server and SQL Server Management Studio tools are essential for proficient database management within the production environment, mirroring the capabilities of a corporate database server. 
<p float="left">
  <img src="https://github.com/ZCHAnalytics/azure-database-migration319/assets/146954022/9fdd2ca0-a20d-47b1-9b0f-14930d4af5b3" width="500" />
  <img src="https://github.com/ZCHAnalytics/azure-database-migration319/assets/146954022/904e8d82-a30d-4b3e-a6df-0b8fc3294b0f?" width="500" /> 
</p>


## Create Production Database
Create the production database by restoring it from a specified backup file. This database is an illustrative and comprehensive sample database that emulates a fictional manufacturing company's operations. It encompasses various tables, views, stored procedures, and data, offering a rich and diverse dataset.

### Saving backup file in the SSMS backup folder: 
<img width="1000" src="https://github.com/ZCHAnalytics/azure-database-migration319/assets/146954022/398ae6e4-52f9-4408-a78f-272f9e08e38a">

### Restoring database from backup:
<img width="1000" src="https://github.com/ZCHAnalytics/azure-database-migration319/assets/146954022/47636c0b-6e6b-41f4-a4fb-456e8a81a077">

### Testing if data is present: 
<img width="1000" src="https://github.com/ZCHAnalytics/azure-database-migration319/assets/146954022/4d488651-436d-4685-b4a5-dfd73fc7b25f">
