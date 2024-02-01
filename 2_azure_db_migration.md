# Set up an Azure SQL Database

## Task 1: Create an Azure SQL Database, which will serve as the target for migrating  on-premise database.
Ensure that the associated SQL Server uses SQL login as the chosen authentication method. 
![image](https://github.com/ZCHAnalytics/azure-database-migration319/assets/146954022/46391c24-75b8-433d-b9ca-16c1093ccc67)

Added Entra ID in Visual Studio Code: ?
![image](https://github.com/ZCHAnalytics/azure-database-migration319/assets/146954022/ca2bc1be-ffcc-47b6-880d-e7915a63cab5)

Firewall rule:?
![image](https://github.com/ZCHAnalytics/azure-database-migration319/assets/146954022/eba62bdc-2700-4f36-b15f-378ddca5684b)

Confirm that the SQL Server has the appropriate firewall rules, specifically with the relevant IP address added to the firewall settings.. 
Azure SQL database connected in Visual Studio Code:
![image](https://github.com/ZCHAnalytics/azure-database-migration319/assets/146954022/281aa30a-00b9-4c54-9ec6-0ff8ac9c635c)


## Task 2: 
Install and configure Azure Data Studio on the production Windows VM. Use this tool to establish a connection to the existing on-premise database.
firewall rule added:

![image](https://github.com/ZCHAnalytics/azure-database-migration319/assets/146954022/d340be49-be57-4596-b117-e45344fe5ae9)

Connected to on_premise database adventuresworks (created from a backup file)
![image](https://github.com/ZCHAnalytics/azure-database-migration319/assets/146954022/b6ca324f-a84e-4903-ac4c-3fab788d7ace)


## Task 3:

Use Azure Data Studio to establish a connection to the newly created Azure SQL Database. This connection servers as the conduit for schema and data migration between the two databases.
Connected to Azure SQL Server:
![image](https://github.com/ZCHAnalytics/azure-database-migration319/assets/146954022/77ac2aed-261c-42a4-a8f6-aaeebcf5c242)

## Task 4:
After establishing connections to both databases, compare and subsequently migrate the schema from the on-premise database to the Azure SQL Database.

### 4.1. SQL Server Schema Compare extension. This extension simplifies the comparison and synchronization of database schemas, making it a valuable tool for seamless database migration.
![image](https://github.com/ZCHAnalytics/azure-database-migration319/assets/146954022/6110e29a-72bc-4f9b-bc4c-47a0d3484391)


Configure the source connection to your local SQL Server database and the target connection to your Azure SQL Database and compare schemas:
![image](https://github.com/ZCHAnalytics/azure-database-migration319/assets/146954022/56f67346-560d-4dff-a75f-a3d79e0020dd)

Apply the selected schema changes to synchronize the schema between the local database and the Azure SQL Database project: 
![image](https://github.com/ZCHAnalytics/azure-database-migration319/assets/146954022/7be652eb-8f31-4556-adfb-bcfe27a2bd96)

'Apply schema compare changes succeeded' message:
![image](https://github.com/ZCHAnalytics/azure-database-migration319/assets/146954022/a142288c-3749-4b7f-8ba5-54aad507de0a)

## Task 5: Data Migration:
Azure SQL Migration extension, a powerful tool for the smooth transfer of data from on-premise database to the Azure SQL Database.
![image](https://github.com/ZCHAnalytics/azure-database-migration319/assets/146954022/9c5e1172-6720-4971-8bfc-df237efedf46)

Create Azure SQL Database Migration Service, which will orchestrate the database migration:
![image](https://github.com/ZCHAnalytics/azure-database-migration319/assets/146954022/19e1bfc4-fe48-48b3-910b-2ba979edc864)

Register the integration runtime, using one of the two keys provided in Azure Data Studio:

Launch Configuration Manager to finalize setting up Runtime Integration:
After Run Validation:
![image](https://github.com/ZCHAnalytics/azure-database-migration319/assets/146954022/419d80c6-ec01-472c-8857-0720d1f746ef)

Migration complete:
![image](https://github.com/ZCHAnalytics/azure-database-migration319/assets/146954022/e5c11b73-7df9-415d-a7c4-adfab5431df4)

## Task 6: 
Confirm the success of the database migration process, carry out a comprehensive validation. 
Thoroughly inspect the data, schema, and any configurations of the migrated database, ensuring that the migration has been executed successfully and adheres to principles of data integrity.
checking schema of both databases:
![image](https://github.com/ZCHAnalytics/azure-database-migration319/assets/146954022/1f303eac-c25f-4ae1-9a36-82661b6cc0d5)

migrated database has fire rules and migration status tables

Comparing columns names and datatypes in both databases:
![image](https://github.com/ZCHAnalytics/azure-database-migration319/assets/146954022/95e3e97c-78a2-4f0d-8c46-17607b4f2652)
