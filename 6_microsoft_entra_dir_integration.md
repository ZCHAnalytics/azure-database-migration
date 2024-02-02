# 
## Task 1: Configure Microsoft Entra ID for Azure SQL Database
Enable Microsoft Entra ID authentication for the SQL Server that hosts the Azure SQL production database. This steps integrates Microsoft Entra ID as a trusted identity provider, allowing users to authenticating using their Microsoft Entra credentials.
--Navigate to the Azure portal and open the SQL Server that hosts the primary database:
![image](https://github.com/ZCHAnalytics/azure-database-migration319/assets/146954022/d3ef9321-2cb0-4cee-9978-66720f05a090)

-- Set Admin
![image](https://github.com/ZCHAnalytics/azure-database-migration319/assets/146954022/d5c4f029-ccf7-4608-8b09-955a8754480d)
Subsequently, choose an Microsoft Entra admin who holds privileged permissions within the Azure SQL Database environment. This admin will have authority over user management and access control. 

test this by connecting to the primary database using Azure Data Studio. 

Establish a connection to the production database using Microsoft Entra credentials within Azure Data Studio.
![image](https://github.com/ZCHAnalytics/azure-database-migration319/assets/146954022/ce867af5-ba32-42a7-9cb5-252edd0219b3)

Add account:
![image](https://github.com/ZCHAnalytics/azure-database-migration319/assets/146954022/51d5ddbb-0069-4ae5-956c-b265a88f5f9f)


## Task 2: Create DB Reader User

