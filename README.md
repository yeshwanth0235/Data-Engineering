# An End-to-End solution for Migrating the data from on-prem to cloud
![image](https://github.com/yeshwanth0235/Data-Engineering/assets/82562647/5ba251cf-ab78-4db9-9b39-0c45d33e3d9f)

1.ADF - 
			ETL tool(Extract, Transform and Load) - for data ingestion it will connect to an on-prem server to copy the tables from the cloud and move the tables to the cloud, Linked service between the the on-prem and cloud is created to transfer the data
   ![image](https://github.com/yeshwanth0235/Data-Engineering/assets/82562647/f8705b2e-38b8-4814-80ee-632176125e7d)
   ![image](https://github.com/yeshwanth0235/Data-Engineering/assets/82562647/f113d587-a243-4210-a42d-29bd4fe872ef)

2.ADLS - 
			ADLS is a fully managed cloud storage service that can be used to store large amounts of data. In this project, ADLS is used as a staging area for the data that is extracted from the on-premises server, connecting ssms through ADF and copy the data through the pipeline to ADLS(bronze file)

3.Databricks - 
			One the data is arrived into the ADLS then we use databricks to transfom the data according to our requirement here in the project the we are doing two levels are transformation

			i)  Bronze to Silver - Here as the data comes from RDBMS system the data is clean, so i have dome done data related changes as the data was recoded with time stamp so removed the time stamp for the analytical purposes and modifying the datatypes
			ii) Silver to Gold   - After that changing the headers according to our needsminor tweakings for readability

With this i have created a lake level architecture
![image](https://github.com/yeshwanth0235/Data-Engineering/assets/82562647/5bc9c2dc-3528-4897-b6c6-f02a42b6bcad)


4.Azure Synapse analytics- 
			So as the data is in the cleanest format so with the help of synapse analytics creating a sql server database and loading the tables from the gold container to sql server with this step the data is completly migrated

5.Power BI - 
			Power BI is a business intelligence (BI) tool that can be used to visualize and analyze data. In this project, Power BI is used to create a dashboard that allows users to view the transformed data.
![image](https://github.com/yeshwanth0235/Data-Engineering/assets/82562647/7af2a5e6-b8fb-4ff6-96d8-f3e4499f135e)

6.Azure AD and Key Vault -
			Azure Active Directory (AD) is a cloud-based identity and access management service. In this project, Azure AD is used to secure the access to the data. Key Vault is a cloud-based service for storing secrets. In this project, Key Vault is used to store the credentials for accessing the data.
