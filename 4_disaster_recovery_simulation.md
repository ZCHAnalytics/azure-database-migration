# Disaster Recovery Simulation  ⚡

## 1.  Mimic data loss in production environment
❗ When mimicking data loss scenarios, we need to exercise caution to avoid unintended consequences and take some precautions. 
### 1.1. Use non-production environments:
We perform data loss testing in non-production environments to prevent any impact on live data and operations:
![image](https://github.com/ZCHAnalytics/azure-database-migration319/assets/146954022/31ac5f50-088e-46eb-88de-b7eabbfb98fb)
### 1.3.  Create backups and documentation: 
We created full backup file with one copy stored on a local server and one in the cloud blob container and documented every step of the process (in this project they are provided in the form of screenshots).

### 1.2. Involve stakeholders:
📧 We inform relevant stakeholders about the testing process to avoid misunderstandings and maintain transparency.

      **SAMPLE COMMUNICATION** 

      Dear colleagues, 
      
      We will be conducting a Database Disaster Recovery Exercise over the upcoming weekend, starting at 18:00 pm and concluding by 11:59 pm on 3 February.

      This exercise aims to test and ensure the effectiveness of our disaster recovery procedures, helping us enhance our system's resilience and reduce downtime in case of unforeseen events.

      Impact on Operations:

      During this period, there may be a temporary disruption in database access. However, we have taken measures to limit any impact on normal business operations.

      Our support team will be available to address any queries.

      We appreciate your understanding and cooperation in this matter. 
      
      If you have any concerns or require further information, please feel free to contact the support team at aicore@ai.core. 

      Thank you for your attention to this important exercise.
      
      Best Regards,
    
### 1.4.  Confirm data deletion and corruption:
We deleted the column 'Title' in the table 'Person' and replaced all values in the column 'City' in the table 'address' with 'Not Known'.
<p float="left">
  <img src="https://github.com/ZCHAnalytics/azure-database-migration319/assets/146954022/5892fdf8-7b76-4085-ab97-bf99a28727b8" width="500"/>
  <img src="https://github.com/ZCHAnalytics/azure-database-migration319/assets/146954022/f1140b0d-d80b-4af1-a568-737c4f3078e0" width="500"/>
</p>  

## 2.  ☁️ Restore database from the cloud backup 
### 2.1. In the Azure storage, we locate the target database that needs restoration and proceed to restoring it:
![image](https://github.com/ZCHAnalytics/azure-database-migration319/assets/146954022/94901c28-9208-4c9b-82a9-751559200eea)

### 2.2.  We check the values in the column 'City' have been restored 👍:
![image](https://github.com/ZCHAnalytics/azure-database-migration319/assets/146954022/6a9ba8c2-20cc-4f86-8036-25d9a1b69a43)

### 2.3.  We check the presence of deleted column 'Title' 👍:
![image](https://github.com/ZCHAnalytics/azure-database-migration319/assets/146954022/796e5308-bfc7-4086-a03a-fdc39cf247df)

### 2.4. We then remove the corrupted database:
![image](https://github.com/ZCHAnalytics/azure-database-migration319/assets/146954022/caf93452-ebb6-46e1-af1a-f898067d0087)
