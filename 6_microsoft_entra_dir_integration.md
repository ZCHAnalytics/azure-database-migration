# Microsoft Entra ID and User Management 
We need to enable Microsoft Entra ID authentication for the SQL Server that hosts the Azure SQL production database. This steps integrates Microsoft Entra ID as a trusted identity provider, allowing users to authenticate using their Microsoft Entra credentials.

## 1.  Configure Microsoft Entra ID for Azure SQL database
### 1.1.  We open the SQL server that hosts the primary database in the Azure portal ☁️:
![image](https://github.com/ZCHAnalytics/azure-database-migration319/assets/146954022/d3ef9321-2cb0-4cee-9978-66720f05a090)

### 1.2.  📝 We select a Microsoft Entra admin who will have authority over user management and access control: 
![image](https://github.com/ZCHAnalytics/azure-database-migration319/assets/146954022/d5c4f029-ccf7-4608-8b09-955a8754480d)

### 1.3.  We test the user by using their Microsoft Entra ID credentials to connect to the primary database in Azure Data Studio: 
![image](https://github.com/ZCHAnalytics/azure-database-migration319/assets/146954022/ce867af5-ba32-42a7-9cb5-252edd0219b3)

### 1.4.  Connection was set up successfully: 
![image](https://github.com/ZCHAnalytics/azure-database-migration319/assets/146954022/51d5ddbb-0069-4ae5-956c-b265a88f5f9f)

## 2. 📗 We create DB Reader User with read-only privileges nd test their access 
### 2.1.  In the Azure Portal, we generate a new user account with reading rights:
![image](https://github.com/ZCHAnalytics/azure-database-migration319/assets/146954022/fcb55e68-9ca3-492c-b3b5-17315e4373c2)

### 2.2.  In the Azure Data Studio, we assign the db_datareader role to the previously created user:
![image](https://github.com/ZCHAnalytics/azure-database-migration319/assets/146954022/70e2ee5f-0cc6-4856-bd61-686ded5e5e5b)

### 2.3.  We disconnect admin user from the database in Azure Data Studio:
![image](https://github.com/ZCHAnalytics/azure-database-migration319/assets/146954022/9cf0963a-d030-42ed-a2e4-7e3c5fa2d0ab)

### 2.4.  We reconnect to the database using the Microsoft Entra ID credentials of the new user:
When adding new account, the user is asked to change their password on the first sign-in:
![image](https://github.com/ZCHAnalytics/azure-database-migration319/assets/146954022/4a4e7cac-742a-4346-a785-deb23904346c)

### 2.5.  We test if the user can change data to ensure the correct role has been assigned to this user:
The user tried to change values in column 'City' in table 'Address' but received a message that they do not have permission to do so. 👍
![image](https://github.com/ZCHAnalytics/azure-database-migration319/assets/146954022/9e00c509-7b5a-44f0-abd6-d30d6c25d484)

