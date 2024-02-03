# Project: Azure Database Management (Migration, Backup, Disaster Recovery, Geo-replication and User Management)

This project designs and implements a cloud-based database system on Microsoft Azure, as this diagram describes: 

![image](https://github.com/ZCHAnalytics/azure-database-migration319/assets/146954022/c3c2b68b-e73f-42b6-961c-0d1bae802c85)

We first identify database on company premises that requires migration to the cloud. This database is located on company server, depicted as 'production-vm' in the diagram. I the company environment the database is run on SQL server and is managed by SQL Server Management Service. Additionally, the company needs to utilise Azure Data Studio for managing the migration from on-premise servers to the cloud.    

The production-vm is a virtual machine created for the purposes of this project. The steps for simulating production envrioment are described in the folder 1.0_production_environment.md. 

## Step 1: Creating a cloud database 
In order to migrate the on-premises database, we first need to create a target database, called SQL production database in the cloud with its own server, called my-server, geographically based in UK South as the nearest region to ensure maximum reliability and cost-effectiveness. We manage migration from the company premises to the cloud using Azure Data Studio and its two extensions called Schema Compare and Migration Service. 

For details of migration set-up, process and success testing, please see file 2.0_azure_database_migration.md

## Step 3: Data Backup and Restore on the premises
We proceed creating two back up options for restoring the database. One is a file BAK stored on company servers and another one is placed in the cloud storage account as in a Azure blob storage container. Additionally, we create a development environment where we can safely test new features, such as for extampl, maintenance scheduling, without such tests impacting company operations using main production data in any way. We then test setting up weekly routine backup to cloud storage. 

Please see file 3.0_data_back_and_restore.md

## Step 4: Disaster Recovery Simulation
We use the development environemnt for this simulation. In this environemnt we intentionally corrupt and delete some data. We then restore data from the cloud back up file whilst removing the corrupted database. 
4.0_disaster_recover_simulation.md

## Step 5: Geo-Replication and Failover
We create a replica server in a different locaiton, US East, to host a replica production database. We then test switching the company use of the dataabase from the UK to US. After testing the database works as inteneded, we carry out switch mack to the original locaiton, UK SOuth. 

5.0_georeplication_and_failover.md 

## Step 6: Microsoft Entra ID and User Management
lastly we configure Microsfot Entra authentication enabling users to use their MIcrosfot crednetials to access the database. We create and admin user as a database owner and a user who can read the data in the database but is not authorise to change or delete any data. 
6.0_microsoft_entra.md
