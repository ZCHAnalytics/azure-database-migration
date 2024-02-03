# Project: Azure Database Management (Migration, Backup, Disaster Recovery, Geo-replication and User Management)

This project designs and implements a cloud-based database system on Microsoft Azure, as this diagram describes: 

![image](https://github.com/ZCHAnalytics/azure-database-migration319/assets/146954022/c3c2b68b-e73f-42b6-961c-0d1bae802c85)

## Base step: 
We first identify database on company premises that requires migration to the cloud. This database is located on company server, depicted as 'production-vm' in the diagram. It the company environment the database is run on SQL server and is managed by SQL Server Management Service. Additionally, the company needs to utilise Azure Data Studio for managing the migration from on-premise servers to the cloud.
![Azure_onpremises](https://github.com/ZCHAnalytics/azure-database-migration319/assets/146954022/8d20e857-2813-4bd5-867b-3fac95a627f3)

The production-vm is a virtual machine created for the purposes of this project. The steps for simulating production envrioment are described in the folder 1.0_production_environment.md. 


## Step 1: Creating a cloud database 
In order to migrate the on-premises database, we first need to create a target database, called SQL production database in the cloud with its own server, called my-server, geographically based in UK South as the nearest region to ensure maximum reliability and cost-effectiveness. We manage migration from the company premises to the cloud using Azure Data Studio and its two extensions called Schema Compare and Migration Service. 
![Azure_migration](https://github.com/ZCHAnalytics/azure-database-migration319/assets/146954022/fee603d9-4d76-4268-9a9d-d41acd7bc516)

For details of migration set-up, process and success testing, please see file 2.0_azure_database_migration.md

## Step 3: Data Backup and Restore on the premises
We proceed creating two back up options for restoring the database. One is a file BAK stored on company servers.
![Azure_bak_restore](https://github.com/ZCHAnalytics/azure-database-migration319/assets/146954022/feb85c85-fb77-4e4f-b6b6-62c0d530240b)

Another one is placed in the cloud storage account as in a Azure blob storage container. 
![Azure_blob](https://github.com/ZCHAnalytics/azure-database-migration319/assets/146954022/157dc84b-3a41-4e89-903c-f1a44190a929)

Additionally, we create a development environment where we can safely test new features, such as for extampl, maintenance scheduling, without such tests impacting company operations using main production data in any way. 
![Azure_testing_maintenance](https://github.com/ZCHAnalytics/azure-database-migration319/assets/146954022/e7173584-a386-42c5-a254-2a13446b0667)

We then test setting up weekly routine backup to cloud storage. 
![Azure_SSMS_plan](https://github.com/ZCHAnalytics/azure-database-migration319/assets/146954022/1651e542-747d-4569-acf2-dcb911b72c62)

Please see file 3.0_data_back_and_restore.md

## Step 4: Disaster Recovery Simulation
We use the development environemnt for this simulation. In this environemnt we intentionally corrupt and delete some data. We then restore data from the cloud back up file whilst removing the corrupted database. 
4.0_disaster_recover_simulation.md
![Azure_migration_recovery](https://github.com/ZCHAnalytics/azure-database-migration319/assets/146954022/8fe0da6e-829c-4e3a-b1c0-f25a17fa2ab9)

## Step 5: Geo-Replication and Failover
We create a replica server in a different location, US East, to host a replica production database. We then test switching the company use of the dataabase from the UK to US. After testing the database works as inteneded, we carry out switch mack to the original locaiton, UK SOuth. 
![Azure_replica](https://github.com/ZCHAnalytics/azure-database-migration319/assets/146954022/d1c4098b-fb90-4153-9863-9d579dd08142)

5.0_georeplication_and_failover.md 

## Step 6: Microsoft Entra ID and User Management
lastly we configure Microsfot Entra authentication enabling users to use their MIcrosfot crednetials to access the database. We create and admin user as a database owner and a user who can read the data in the database but is not authorise to change or delete any data. 
![Azure_entra](https://github.com/ZCHAnalytics/azure-database-migration319/assets/146954022/bf435048-0e8f-4aa9-b607-4a5314fae742)

6.0_microsoft_entra.md
