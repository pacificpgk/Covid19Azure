# Covid19Azure

ECDC (European Center for Disease Prevention & Control) colects and shares various kind of data related to Covid-19 cases, deaths, hospitalization, tests and cases reported across Europe.
Following are the purpose of this project:
 1. Ingest data from ECDC into Azure Data Factory.
 2. Store the ingested data in Azure Data Lake.
 3. Apply suitable transformations on the data using dataflow in Azure Data Factory.
 4. Transformations include derivations and filteration of data.
 5. Transformed data is stored in Azure SQL DB.
 6. Power BI is used to import the data from Azure SQL and generate meaningful insights through visualisation.
 
 
# High Level Architecture

![image](https://user-images.githubusercontent.com/30026192/148900408-10234755-77db-4654-b4f7-05c5dc2e0078.png)

Data sources:

SmartFoods Rest API:
Type	Rest API
Authentication	Oauth2
Data Endpoints	
Order line Transactions (CSV)

Customers (JSON)

Auth Token (JSON)

Frequency	Daily
Documentation	https://github.com/Mmodarre/retailDataGeneratorAzureFunction
SmartFoods Items
Type	On premises Local file system
Authentication	NA
Data Endpoints	
Food (CSV)

Food-Nutrition (CSV)

Nutrition (CSV)

Frequency	NA – One Off
Documentation	
WWI OLTP
Type	SFTP
Authentication	Username/Password
Data Endpoints	
Orderline Transactions (Parquet)

Orders Transactions (Parquet)

Customers (Parquet)

Frequency	Daily
Documentation	
