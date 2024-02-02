# Disaster Recovery Simulation

## Task 1: Mimic Data Loss in Production Environment
Deliberately remove critical data from the production database to replicate a scenario where data integrity is compromised. 

Ensure that you document this simulated data loss meticulously. This documentation will serve as a blueprint for the recovery testing.
### Precautions When Mimicking Data Loss
When mimicking data loss scenarios, exercise caution to avoid unintended consequences. Follow these precautions:
-  Use Non-Production Environments: Perform data loss testing in non-production environments to prevent any impact on live data and operations
1.1 Azure Virtual Machine was created under the name test-vm with Azure Data Studio installed and other tools.  
![image](https://github.com/ZCHAnalytics/azure-database-migration319/assets/146954022/31ac5f50-088e-46eb-88de-b7eabbfb98fb)

Azure Data Studio should have a connection establish to a production Azure SQL Database, which hosts adventure-works-before database.
![image](https://github.com/ZCHAnalytics/azure-database-migration319/assets/146954022/0d993893-0355-43d3-b283-e965d649dba9)

-  Involve Stakeholders: Inform relevant stakeholders about the testing process to avoid misunderstandings and maintain transparency
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
After completing the simulation, confirm its success by examining the Azure SQL Database using the connection already established in Azure Data Studio.

-- Intentional deletion
![image](https://github.com/ZCHAnalytics/azure-database-migration319/assets/146954022/5892fdf8-7b76-4085-ab97-bf99a28727b8)

-- Intentional Data Corruption
![image](https://github.com/ZCHAnalytics/azure-database-migration319/assets/146954022/290d5511-ff50-4698-b7b2-67cef926261a)
City value replaced with 'Not Known'
![image](https://github.com/ZCHAnalytics/azure-database-migration319/assets/146954022/f1140b0d-d80b-4af1-a568-737c4f3078e0)


## Task 2: Restore Database from Azure SQL Database Backup 
Navigate to the Azure portal and from the Azure SQL Database dashboard, locate and select the target database that needs restoration.
From the SQL Database Home Page select the Restore option at the top bar on the page:

Deployment of restored Database in Azure portal:
![image](https://github.com/ZCHAnalytics/azure-database-migration319/assets/146954022/94901c28-9208-4c9b-82a9-751559200eea)

### Set connection to restored database using Azure Data Studio.
City restored
![image](https://github.com/ZCHAnalytics/azure-database-migration319/assets/146954022/6a9ba8c2-20cc-4f86-8036-25d9a1b69a43)

Column 'Title' restored:
![image](https://github.com/ZCHAnalytics/azure-database-migration319/assets/146954022/796e5308-bfc7-4086-a03a-fdc39cf247df)


Corrupted database removed:
![image](https://github.com/ZCHAnalytics/azure-database-migration319/assets/146954022/caf93452-ebb6-46e1-af1a-f898067d0087)


