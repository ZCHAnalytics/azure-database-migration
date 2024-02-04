# Set up an Azure SQL Database ☁️ 

## 1. Create an Azure SQL Database in the cloud, which will serve as the target for migrating  on-premise database
### 1.1.  An Azure SQl Database was created using SQL login as the chosen authentication method 🔑: 
![image](https://github.com/ZCHAnalytics/azure-database-migration319/assets/146954022/46391c24-75b8-433d-b9ca-16c1093ccc67)

### 1.2.  Set firewall rule 🔥 in Visual Studio Code
![image](https://github.com/ZCHAnalytics/azure-database-migration319/assets/146954022/eba62bdc-2700-4f36-b15f-378ddca5684b)

### 1.3.  Connect to Azure SQL database in Visual Studio Code
![image](https://github.com/ZCHAnalytics/azure-database-migration319/assets/146954022/281aa30a-00b9-4c54-9ec6-0ff8ac9c635c)

## 2.  Prepare for migration 
### 2.1.  Configure Azure Data Studio on the production Windows 🏢: 
Install and connect Azure Data Studio to the cloud database.
![image](https://github.com/ZCHAnalytics/azure-database-migration319/assets/146954022/b6ca324f-a84e-4903-ac4c-3fab788d7ace)

## 3.  Connect to Azure SQL Database
Use Azure Data Studio to establish a connection to the newly created Azure SQL Database. This connection servers as the conduit for schema and data migration between the two databases.
![image](https://github.com/ZCHAnalytics/azure-database-migration319/assets/146954022/77ac2aed-261c-42a4-a8f6-aaeebcf5c242)

## 4.  Migrate local schema
### 4.1.  Install SQL Server Schema Compare extension:
![image](https://github.com/ZCHAnalytics/azure-database-migration319/assets/146954022/6110e29a-72bc-4f9b-bc4c-47a0d3484391)
### 4.2.  Compare schemas of the local SQL Server database and the cloud SQL database ☁️:
![image](https://github.com/ZCHAnalytics/azure-database-migration319/assets/146954022/56f67346-560d-4dff-a75f-a3d79e0020dd)
### 4.3.  Synchronise the schema between the local database and the cloud database ☁️: 
![image](https://github.com/ZCHAnalytics/azure-database-migration319/assets/146954022/7be652eb-8f31-4556-adfb-bcfe27a2bd96)
### 4.3.  Confirm the successful application of schema compare changes:
![image](https://github.com/ZCHAnalytics/azure-database-migration319/assets/146954022/a142288c-3749-4b7f-8ba5-54aad507de0a)

## 5.  Migrate the company database to the cloud
### 5.1.  Install Azure SQL Migration extension:
![image](https://github.com/ZCHAnalytics/azure-database-migration319/assets/146954022/9c5e1172-6720-4971-8bfc-df237efedf46)
### 5.2.  Orchestrate database migration with Azure SQL Database Migration Service:
![image](https://github.com/ZCHAnalytics/azure-database-migration319/assets/146954022/19e1bfc4-fe48-48b3-910b-2ba979edc864)
### 5.3.  Migration complete:
![image](https://github.com/ZCHAnalytics/azure-database-migration319/assets/146954022/e5c11b73-7df9-415d-a7c4-adfab5431df4)

## 6.  Validation of successful  database migration process ✌️
### 6.1.  Check schemas in both databases:
![image](https://github.com/ZCHAnalytics/azure-database-migration319/assets/146954022/1f303eac-c25f-4ae1-9a36-82661b6cc0d5)
### 6.2.  Compare columns names and their datatypes in both databases:
![image](https://github.com/ZCHAnalytics/azure-database-migration319/assets/146954022/95e3e97c-78a2-4f0d-8c46-17607b4f2652)
