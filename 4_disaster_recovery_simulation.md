# Disaster Recovery Simulation

## Task 1: Mimic Data Loss in Production Environment
Deliberately remove critical data from the production database to replicate a scenario where data integrity is compromised. 

Ensure that you document this simulated data loss meticulously. This documentation will serve as a blueprint for the recovery testing.
### Precautions When Mimicking Data Loss
When mimicking data loss scenarios, exercise caution to avoid unintended consequences. Follow these precautions:
-  Use Non-Production Environments: Perform data loss testing in non-production environments to prevent any impact on live data and operations
1.1 Azure Virtual Machine was created under the name test-vm.  
![image](https://github.com/ZCHAnalytics/azure-database-migration319/assets/146954022/31ac5f50-088e-46eb-88de-b7eabbfb98fb)
1.2. Install sql server and ssms in non-production environment.
- created a back up file. 
-  Backup the Database: Take a backup of the database before initiating any data loss scenarios, ensuring you can revert to a known good state if needed
-  -  Involve Stakeholders: Inform relevant stakeholders about the testing process to avoid misunderstandings and maintain transparency
  #### Sample communication:
Dear colleagues,

We will be conducting a Database Disaster Recovery Exercise over the upcoming weekend, starting at 18:00 pm and concluding by 11:59 pm on 3 February.

This exercise aims to test and ensure the effectiveness of our disaster recovery procedures, helping us enhance our system's resilience and reduce downtime in case of unforeseen events.

Impact on Operations:
During this period, there may be a temporary disruption in database access. However, we have taken measures to limit any impact on normal business operations.

Our support team will be available to address any queries.

We appreciate your understanding and cooperation in this matter. If you have any concerns or require further information, please feel free to contact the support team at aicore@ai.core. 

Thank you for your attention to this important exercise.

Best Regards,

### 
-- Intentional deletion
-- Intentional Data Corruption
![image](https://github.com/ZCHAnalytics/azure-database-migration319/assets/146954022/23b0353b-41c3-434b-b7c0-ebc48b9937b8)

###

Document the Process: Record the steps followed and the outcomes during testing for documentation and analysis
#### Checking the database in Azure Data Studio:
if column 'title' is removed from Person table. 
![image](https://github.com/ZCHAnalytics/azure-database-migration319/assets/146954022/f5a9f43a-3ba9-430d-a002-a3563cc909e7)

if city is set 'not known' in column CIty in the table person.address:
![image](https://github.com/ZCHAnalytics/azure-database-migration319/assets/146954022/efb98857-4186-4b86-9e10-037c0f460990)

After completing the simulation, confirm its success by examining the Azure SQL Database using the connection already established in Azure Data Studio.


## Task 2: Restore Database from Azure SQL Database Backup 
Navigate to the Azure portal and from the Azure SQL Database dashboard, locate and select the target database that needs restoration

From the SQL Database Home Page select the Restore option at the top bar on the page
![image](https://github.com/ZCHAnalytics/azure-database-migration319/assets/146954022/cf6a8819-e112-415f-a682-ccf3d2ff2894)

City restored: 
![image](https://github.com/ZCHAnalytics/azure-database-migration319/assets/146954022/a9803fdc-8290-4ce3-b763-ff8624681ebb)

Column 'Title' restored:
![image](https://github.com/ZCHAnalytics/azure-database-migration319/assets/146954022/9834acf4-b82c-4255-a39e-903b9efbdadb)

Corrupted database removed:
![image](https://github.com/ZCHAnalytics/azure-database-migration319/assets/146954022/b88fef00-d4e6-461b-96f2-9ac223262505)

