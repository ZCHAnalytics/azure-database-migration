# Setting up production environment

## Set up a Windows Virtual Machine (VM)
The cornerstone of the production environment. This VM will emulate the functions of a Windows server, replicating the operations of an on-premise system within a company. Throughout the course of this project, the VM will act as a repository for the company's database. This setup effectively simulates a secure and dedicated data storage solution.

### Ensure the appropriate network settings and firewall rules to establish a connection to the VM using the RDP protocol.
Virtual machine deployed: 
![image](https://github.com/ZCHAnalytics/azure-database-migration319/assets/146954022/ebb07f9b-e09d-4c29-a279-01f16953c154)


## Task 2: Connect to Windows Virtual Machine:
Use the RDP protocol and Microsoft Remote Desktop to establish a secure connection to the VM.
![image](https://github.com/ZCHAnalytics/azure-database-migration319/assets/146954022/7f102506-2b71-49bc-8935-73252a39bd5a)


## Task 3: Install SQL Server and SSMS on Virtual Machine:
SQL Server and SQL Server Management Studio tools are essential for proficient database management within the production environment, mirroring the capabilities of a corporate database server.
Installing SQL Server:
![image](https://github.com/ZCHAnalytics/azure-database-migration319/assets/146954022/9fdd2ca0-a20d-47b1-9b0f-14930d4af5b3)

SSMS:
![image](https://github.com/ZCHAnalytics/azure-database-migration319/assets/146954022/904e8d82-a30d-4b3e-a6df-0b8fc3294b0f)


## Task: 4: Create Production Database
Create the production database by restoring it from a specified backup file that corresponds to the renowned Microsoft SQL Server database known as AdventureWorks. This database is an illustrative and comprehensive sample database that emulates a fictional manufacturing company's operations. It encompasses various tables, views, stored procedures, and data, offering a rich and diverse dataset.
Restoring of the AdventureWorks database from the provided backup file will replicate an authentic production database scenario.
Saving backup file in the SSMS backup folder: 
![image](https://github.com/ZCHAnalytics/azure-database-migration319/assets/146954022/398ae6e4-52f9-4408-a78f-272f9e08e38a)

Restoring database from backup:
![image](https://github.com/ZCHAnalytics/azure-database-migration319/assets/146954022/47636c0b-6e6b-41f4-a4fb-456e8a81a077)

Testing if data is present: 
![image](https://github.com/ZCHAnalytics/azure-database-migration319/assets/146954022/4d488651-436d-4685-b4a5-dfd73fc7b25f)

