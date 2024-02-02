
# Data Backup and Restore


##Task 1: 
Generate a full backup of the production database hosted on the Windows VM. This backup essentially duplicates the database, providing a safety net in the event of unforeseen issues.
Once the backup is complete, store the resultant backup file in a designated location on the computer.
SSMS: database: Tasks: backup

![image](https://github.com/ZCHAnalytics/azure-database-migration319/assets/146954022/211d41d5-969d-43c0-bbf0-f33a130ef1c8)

For creating a backup that can be restored to a development environment, we will choose the Full backup type. Stored on a local computer.
![image](https://github.com/ZCHAnalytics/azure-database-migration319/assets/146954022/2cbbcd75-dbca-477a-aef1-898043e245be)

## Task 2: Upload Backup to Blob Storage
Configure an Azure Blob Storage account that serves as a secure online repository for the database backups.

Upload the previously created database backup file to the Blob Storage container. This step provides an extra layer of backup protection through the presence of a redundant copy stored remotely.

![image](https://github.com/ZCHAnalytics/azure-database-migration319/assets/146954022/984ab1c1-cd3f-4b13-aa98-33c231d1474f)

## Task 3: Restore Database on Development Environment
Provision a new Windows VM that mirrors the development setup. 

Install SQL Server on this VM to mimic the necessary database infrastructure.
Proceed to restore the database backup onto this new "sandbox" environment. This allows you to safely explore and experiment with new concepts, while your main production data remains unaffected.
![image](https://github.com/ZCHAnalytics/azure-database-migration319/assets/146954022/6c3bb893-7b8a-4571-8947-729fae785b2a)

## Task 4: 
On development Windows VM, utilize SSMS to establish a Management Task that automates regular backups of the development database.
Configure a weekly backup schedule to ensure consistent protection for the  evolving work and simplify recovery for the development environment if needed.

maintenance Plan Wizard:

![image](https://github.com/ZCHAnalytics/azure-database-migration319/assets/146954022/df012b42-202c-4ee3-bfbf-4a34ff819af6)

finished setting up weekly backup with container name and its URL:

![image](https://github.com/ZCHAnalytics/azure-database-migration319/assets/146954022/958ca779-763d-443a-b64c-2f357a4679ca)

refresh and check if execute works:

Need to add forward slash in the end of URL:

![image](https://github.com/ZCHAnalytics/azure-database-migration319/assets/146954022/26eb2bd2-f2d5-44c4-b8b8-2382cd740c8a)

![image](https://github.com/ZCHAnalytics/azure-database-migration319/assets/146954022/bdaed841-37cc-4650-bdd8-598102cbecf8)


