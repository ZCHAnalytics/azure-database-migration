# Azure Database Management 
Migration, Backup, Disaster Recovery, Geo-replication and User Management

## Overview
This project focuses on the design and implementation of a cloud-based database system on Microsoft Azure. The diagram below illustrates the process. Please consult files on each step for further details.

<p align="left">
  <img alt="Database Migration Diagram" src="https://github.com/ZCHAnalytics/azure-database-migration319/assets/146954022/c3c2b68b-e73f-42b6-961c-0d1bae802c85">
</p>

||||
|--------------|-------------|--------------|
| |**Replication of an on-premises database** |
| <img alt="creating production environment simulation" width="200" src="https://github.com/ZCHAnalytics/azure-database-migration319/assets/146954022/f531f9c3-d8d2-4847-bd96-aeeb402e75b8"> | For this project, we used a virtual machine to simulate a company environment. The environment contains an SQL server for running the database and an SQL Server Management Service. To prepare for the migration process, we also use Azure Data Studio. For specifics, consult [1_production_environment.md](1_production_environment.md).| <img alt="Adding Azure Data Studio" align="left" width="150" src="https://github.com/ZCHAnalytics/azure-database-migration319/assets/146954022/448a311c-20a3-41e9-8ccd-dd704afe2659">
| | **Migration process**   |        
| **UK SOUTH** <img alt="create SQL server in the UK South" width="100" src="https://github.com/ZCHAnalytics/azure-database-migration319/assets/146954022/540e743a-fbf7-47b8-9203-7c804243f810"> | To ensure reliability and cost-effectiveness, we create a SQL production database on the cloud servers located in the UK South region. Migration is managed through two extensions of Azure Data Studio: Schema Compare and Migration Service. For specifics, consult [2_azure_db_migration.md](2_azure_db_migration.md) | <img alt="Azure Data Studio extensions" align="right" scr="https://github.com/ZCHAnalytics/azure-database-migration319/assets/146954022/75ada7cd-865c-4937-8ddc-8b166e9acf1f">
| | **Data backup and restore on the premises** | |
|<img alt="Data backup locally" width="200" src="https://github.com/ZCHAnalytics/azure-database-migration319/assets/146954022/ff93bd73-d554-4947-b66f-7b031299903c"> | We implement two backup options: a BAK file stored on company servers and another in a cloud storage account within an Azure blob storage container. | <img alt="data backup in the cloud" align="right" width="200" src="https://github.com/ZCHAnalytics/azure-database-migration319/assets/146954022/be46e2e6-57b8-42e3-a184-e4415063f745">
|<img alt="create development environment for testing maintenance" src="https://github.com/ZCHAnalytics/azure-database-migration319/assets/146954022/1db0826d-ee7b-40fa-aa27-c2c75bd96ee2"> | Additionally, we use the development environment to test weekly cloud backup scheduling, without impacting company operations. For specifics, consult [3_data_backup_and_restore.md](3_data_backup_and_restore.md) | <img alt="testing weekly backup scheduling" align="right" src="https://github.com/ZCHAnalytics/azure-database-migration319/assets/146954022/1651e542-747d-4569-acf2-dcb911b72c62"> | 
| |**Disaster recovery simulation**| |
|<img alt="simulate disaster recovery" src="https://github.com/ZCHAnalytics/azure-database-migration319/assets/146954022/8fe0da6e-829c-4e3a-b1c0-f25a17fa2ab9">| In the development environment, we simulate a disaster by intentionally corrupting and deleting data. The recovery process involves restoring data from the cloud backup file while removing the corrupted database. [4_disaster_recovery_simulation.md](4_disaster_recovery_simulation.md) |
| |**Geo-replication and failover**|
|<img alt="creating a replica server in US East" width="200" src="https://github.com/ZCHAnalytics/azure-database-migration319/assets/146954022/d1c4098b-fb90-4153-9863-9d579dd08142">| We establish a server in the US East region to host a replica production database. Testing involves switching database usage between the UK and US, ensuring seamless failover. For specifics, consult [5_georeplication_and_failover](5_georeplication_and_failover.md)|
| |**Microsoft Entra ID and user management** |
|<img alt="Creating read-only user" width="300" src="https://github.com/ZCHAnalytics/azure-database-migration319/assets/146954022/bf435048-0e8f-4aa9-b607-4a5314fae742">| In the final phase, we configure Microsoft Entra authentication, allowing users to access the database using their Microsoft credentials. User roles include a database owner with administrative privileges and a read-only user without authorization to modify or delete data. For specifics, consult [6_microsoft_entra.md](6_microsoft_entra.md)


## License
This project is licensed under the terms of the MIT license.


## Acknowledgments
Special thanks to my AICore support engineers A., B., H., I., I., J., K., M., M., V., W., for their invaluable assistance and latest hacks! This journey wouldn't be as epic without their guidance. 🏆 🏅

