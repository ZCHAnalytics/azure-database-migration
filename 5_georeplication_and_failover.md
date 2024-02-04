# Geo-Replication, Failover and Tailback

## 1.  Geo-replication
We create a synchronised replica of the primary database that resides on a separate SQL server in a different geographical region. This geographical separation is crucial as it bolsters redundancy and resilience, minimizing shared risks.
![image](https://github.com/ZCHAnalytics/azure-database-migration319/assets/146954022/d9ca2a6b-5a9a-44d2-8e87-491428532100)

## 2. Create a failover group
To carry out a failover, a failover group needs to be established.  
### 2.1.  New failover group:
![image](https://github.com/ZCHAnalytics/azure-database-migration319/assets/146954022/fc5548c7-c0f4-449a-ba92-cd3bb42b787b)

### 2.2.  Check the presence of the failover group in the Azure SQL Server for geo-replicated database:
![image](https://github.com/ZCHAnalytics/azure-database-migration319/assets/146954022/b9f6716a-95e5-41bf-9a73-c6ea24aaff4b)

### 2.3.  Check map locations of primary and secondary databases:
![image](https://github.com/ZCHAnalytics/azure-database-migration319/assets/146954022/50a83439-6083-4d0d-aa29-e5fcad9bb8a0)

## 3. Initiate a planned failover (without data loss) 
We simulate real-world challenges by orchestrating a planned failover to the secondary region. This act transitions operations to the secondary copy. 

### 3.1.  Failover started:
![image](https://github.com/ZCHAnalytics/azure-database-migration319/assets/146954022/01bfd676-db83-4639-814d-650d149b114b)

### 3.2.  Failover completed:
![image](https://github.com/ZCHAnalytics/azure-database-migration319/assets/146954022/f269439f-528a-4e0d-9b04-ca7ab2aed02f)

## 4.  Tailback 
After testing failover process, we organise tailback and evaluate the availability and data consistency of the database.

### 4.1. Return the database in the UK South to the role of primary database: 
![image](https://github.com/ZCHAnalytics/azure-database-migration319/assets/146954022/17258300-989d-44ba-9835-66bc3a69e71f)

### 4.2.  Connect to the secondary database using replica server details and check if it is working as expected:
![image](https://github.com/ZCHAnalytics/azure-database-migration319/assets/146954022/31873edf-0a45-4e46-9761-957416f73270)
