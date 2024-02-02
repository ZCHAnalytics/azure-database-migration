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
After completing the simulation, confirm its success by examining the Azure SQL Database using the connection already established in Azure Data Studio.


## Task 2: Restore Database from Azure SQL Database Backup 

