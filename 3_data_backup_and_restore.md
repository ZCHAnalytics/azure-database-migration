# Data Backup and Restore

## 1.  Generate a full backup of the on-premise database 
Using SSMS tool, we create a backup, providing a safety net in the event of unforeseen issues.
![image](https://github.com/ZCHAnalytics/azure-database-migration319/assets/146954022/211d41d5-969d-43c0-bbf0-f33a130ef1c8)


We store the backup on the on-premise server.
![image](https://github.com/ZCHAnalytics/azure-database-migration319/assets/146954022/2cbbcd75-dbca-477a-aef1-898043e245be)


## 2.  Upload backup to blob storage
Upload the previously created database backup file to the blob storage container to provide an extra layer of data protection through the presence of a redundant copy stored remotely.
![image](https://github.com/ZCHAnalytics/azure-database-migration319/assets/146954022/984ab1c1-cd3f-4b13-aa98-33c231d1474f)


## 3.  Restore database on development environment
We provision a "sandbox" environment on a different virtual machine to test new concepts without affecting the company's main production data. We install SSMS to test maintenance tasks for the database. 
![image](https://github.com/ZCHAnalytics/azure-database-migration319/assets/146954022/6c3bb893-7b8a-4571-8947-729fae785b2a)


## 4.   Automate backups for development environment
We need to configure a weekly backup schedule to the cloud to ensure consistent protection for the evolving work and simplify recovery and test this configuration on a specially provisioned development VM.

### 4.1.  Maintenance Plan Wizard:
We utilise SSMS to automates regular backups of the development database:
![image](https://github.com/ZCHAnalytics/azure-database-migration319/assets/146954022/df012b42-202c-4ee3-bfbf-4a34ff819af6)


### 4.2.  We configure a new maintenance schedule for weekly backup to the cloud container:
![image](https://github.com/ZCHAnalytics/azure-database-migration319/assets/146954022/958ca779-763d-443a-b64c-2f357a4679ca)


### 4.3.  We execute the new maintenance plan and check the cloud container if the backup was created successfully:
![image](https://github.com/ZCHAnalytics/azure-database-migration319/assets/146954022/bdaed841-37cc-4650-bdd8-598102cbecf8)
