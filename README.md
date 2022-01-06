# Covid19Azure

ECDC (European Center for Disease Prevention & Control) colects and shares various kind of data related to Covid-19 cases, deaths, hospitalization, tests and cases reported across Europe.
Following are the purpose of this project:
 1. Ingest data from ECDC into Azure Data Factory.
 2. Store the ingested data in Azure Data Lake.
 3. Apply suitable transformations on the data using dataflow in Azure Data Factory.
 4. Transformations include derivations and filteration of data.
 5. Transformed data is stored in Azure SQL DB.
 6. Power BI is used to import the data from Azure SQL and generate meaningful insights through visualisation.
 7. Please refer to AzureDataFactory.pdf for the flow of data.


