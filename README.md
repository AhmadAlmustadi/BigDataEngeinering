# BigDataEngeinering
StackOverflow Data Processing Project
1. About the Data
1.1 Data Background
This dataset is from StackOverflow, a well-known online IT developer community. It records daily online posts, including post types and user information. The dates in the dataset have been modified to be current, so every day you will see today's posts data.

The three tables are located in two data sources: RDS and Azure Storage Blob Container.

RDS: The Users and PostTypes tables are stored in an RDS Postgres database. These are slowly changing tables, updated weekly using SCD type 1 (new records overwrite old records).

Note: You will need some secret values to link to the RDS and Azure Blob Storage.
Azure Storage Blob: The daily Posts data files are in parquet format, stored under the storage account wcddestorageexternal, in the container de-project-st, and the folder Posts_today.

2. Business Requirements
Create a Data Lake:
Create an Azure Data Factory to handle data ingestion and processing.
Connect to an AWS RDS Postgres database to ingest the PostTypes and Users tables into your Data Lake weekly.
Connect to a WeCloudData Azure blob container to copy the parquet files of Posts from StackOverflow into your Data Lake daily.
3. Machine Learning Process Requirements
Create a Databricks notebook to process data and feed it into a Machine Learning Model, then output the results.
The model should read the text in the Posts files, classify the topics, and use Spark to generate a file listing all today's topics ordered by frequency.
4. Chart Requirements
Create a chart in Azure Synapse based on the output data from the Machine Learning Model to display the top 10 topics of the day.
5. Project Infrastructure
In this project, all infrastructure is built on Azure.

Azure Data Lake: Used for storing ingested Posts, PostTypes, and Users files; storing the data file for Machine Learning; and storing the output data file after Machine Learning.
Azure Data Factory (ADF): Manages the entire pipeline from data ingestion and transformation to Machine Learning job execution.
Azure Synapse: Platform for data analysis and visualization.
