## Task 1: Set up a Geo-Replication for Azure SQL Database

Set up geo-replication for the production Azure SQL Database. Creates a synchronized replica of the primary database.

This replica will reside on a separate SQL server located in a different geographical region from your primary database server. This geographical separation is crucial as it bolsters redundancy and resilience, minimizing shared risks.
Find primary database and select replicas:
![image](https://github.com/ZCHAnalytics/azure-database-migration319/assets/146954022/2c2307f0-4bba-4de2-9014-9c3b198b9be8)

Create a replica database on a new server in a different region, East US 
![image](https://github.com/ZCHAnalytics/azure-database-migration319/assets/146954022/d9ca2a6b-5a9a-44d2-8e87-491428532100)



## Task 2: Test Failover and Fallback
Simulate real-world challenges by orchestrating a planned failover to the secondary region. This act transitions operations to the secondary copy. Evaluate the availability and data consistency of the failover database.
- select server in the UK South in Azure Portal:
- 
Select Failover groups under the Data management pane
![image](https://github.com/ZCHAnalytics/azure-database-migration319/assets/146954022/022808d3-90cf-44f1-a308-c31b2e9a4791)

-- then select Add group to create a new failover group
![image](https://github.com/ZCHAnalytics/azure-database-migration319/assets/146954022/fc5548c7-c0f4-449a-ba92-cd3bb42b787b)

-- navigate to the Azure SQL Server for secondary/replication database, under failover group there is a adventure-replica-group:
![image](https://github.com/ZCHAnalytics/azure-database-migration319/assets/146954022/b9f6716a-95e5-41bf-9a73-c6ea24aaff4b)
-- map
![image](https://github.com/ZCHAnalytics/azure-database-migration319/assets/146954022/50a83439-6083-4d0d-aa29-e5fcad9bb8a0)

-- To initiate a planned failover (without data loss), select Failover from the task pane to fail over your failover group containing your database. 
![image](https://github.com/ZCHAnalytics/azure-database-migration319/assets/146954022/01bfd676-db83-4639-814d-650d149b114b)

-- Failover in progress:
![image](https://github.com/ZCHAnalytics/azure-database-migration319/assets/146954022/124c4654-00e5-44e4-b1d3-4840c1c5ea8f)

-- Failover completed
![image](https://github.com/ZCHAnalytics/azure-database-migration319/assets/146954022/f269439f-528a-4e0d-9b04-ca7ab2aed02f)

--  Failover back
![image](https://github.com/ZCHAnalytics/azure-database-migration319/assets/146954022/17258300-989d-44ba-9835-66bc3a69e71f)

-- use the connection details of the secondary server to connect to the new primary database, and run tests to validate the database's functionality in the secondary region, ensuring that it is working as expected
![image](https://github.com/ZCHAnalytics/azure-database-migration319/assets/146954022/44a729d9-0407-423e-a84c-69e69ed0dd3e)

Connected to the database usign replica server details on Azure Data Studio:
![image](https://github.com/ZCHAnalytics/azure-database-migration319/assets/146954022/31873edf-0a45-4e46-9761-957416f73270)




Afterward, perform a failback to the primary region, demonstrating the cyclical nature of the failover strategy.
