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
Generate a new user account in Microsoft Entra ID, which will serve as a DB Reader user.
![image](https://github.com/ZCHAnalytics/azure-database-migration319/assets/146954022/fcb55e68-9ca3-492c-b3b5-17315e4373c2)

In Azure Data Studio, ensure there is a connection to the production database using the Microsoft Entra admin credentials. 
![image](https://github.com/ZCHAnalytics/azure-database-migration319/assets/146954022/1567dff5-0bd1-453d-9639-886c374ae405)

Assign the db_datareader role to the previously created DB Reader User. This role provides the user with read-only privileges.
![image](https://github.com/ZCHAnalytics/azure-database-migration319/assets/146954022/70e2ee5f-0cc6-4856-bd61-686ded5e5e5b)

Disconnect from the database in Azure Data Studio:
![image](https://github.com/ZCHAnalytics/azure-database-migration319/assets/146954022/9cf0963a-d030-42ed-a2e4-7e3c5fa2d0ab)

Reconnect to the production database using Azure Data Studio and the credentials of the new DB Reader AD user. 
When adding new account, changes password:
![image](https://github.com/ZCHAnalytics/azure-database-migration319/assets/146954022/4a4e7cac-742a-4346-a785-deb23904346c)
post sign-in screen:
![image](https://github.com/ZCHAnalytics/azure-database-migration319/assets/146954022/cb0dcdee-e18b-40d5-83f5-a2eed604663d)

Test out the permissions of the user to ensure the correct role has been assigned to this user.
Able to read a table Person.Address
![image](https://github.com/ZCHAnalytics/azure-database-migration319/assets/146954022/e7648632-8440-4297-8323-28df47efa3b1)

Permission denied to change values in column 'City' in table 'Address':
![image](https://github.com/ZCHAnalytics/azure-database-migration319/assets/146954022/9e00c509-7b5a-44f0-abd6-d30d6c25d484)

