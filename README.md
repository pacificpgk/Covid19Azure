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

# Data sources:

<table>
    <thead>
        <tr>
            <th>Source Dataset Name</th>
            <th>Source File Name</th>
            <th>Linked Service Name</th>
            <th>Target Dataset Name</th>
            <th>Target File Name</th>
            <th>Source</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>ds_population_raw_gz</td>
            <td>population_by_age.tsv.gz</td>
            <td>ls_blob_covid19reportingstoac</td>
            <td>ds_population_raw_tsv</td>
            <td>population_by_age_tsv</td>
            <td>Downloaded File</td>
        </tr>
        <tr>
            <td rowspan=2>ds_ecdc_raw_http</td>
            <td>cases_deaths.csv</td>
            <td rowspan=5>ls_dl_covid19reportingdtlk</td>
            <td rowspan=2>ds_ecdc_raw_csv_dl</td>
            <td>cases_deaths.csv</td>
            <td>Github Site</td>
        </tr>
        <tr>
            <td>hospital_admissions.csv</td>
            <td>hospital_admissions.csv</td>
            <td>Github Site</td>
        </tr>
        <tr>
            <td rowspan=3>NA</td>
            <td rowspan=3>NA</td>
            <td>ds_raw_testing</td>
            <td>testing.csv</td>
            <td>Downloaded File</td>
        </tr>
        <tr>
            <td>ds_country_lookup</td>
            <td>country_lookup.csv</td>
            <td rowspan=2>Lookup File</td>
        </tr>
        <tr>
            <td>ds_dim_date_lookup</td>
            <td>dim_date.csv</td>
        </tr>
    </tbody>
</table> 

# Linked Service:
ls_blob_covid19reportingstoac
![image](https://user-images.githubusercontent.com/30026192/148940127-77736fe9-c9fc-4f85-8603-3526f156f9e8.png)

ls_dl_covid19reportingdtlk
![image](https://user-images.githubusercontent.com/30026192/148940255-5940b9f6-6527-49bd-a559-db0da6b1f266.png)

ls_http_ecdc_eu_data
![image](https://user-images.githubusercontent.com/30026192/148940545-351fa4f9-145b-4ad6-a83b-6bc094063de0.png)

#Ingest Population Data:
![image](https://user-images.githubusercontent.com/30026192/148941394-ac7dbb3d-d3a0-46df-a057-915c4970d651.png)

![image](https://user-images.githubusercontent.com/30026192/148941487-4498eedb-1671-4712-b8e9-d7358ec6f913.png)

![image](https://user-images.githubusercontent.com/30026192/148941632-d07f5de6-d626-44b2-b8fa-56dedfaa2443.png)

![image](https://user-images.githubusercontent.com/30026192/148941706-ce9a7efa-f7d5-458f-b3c0-f8975ffc6ec6.png)

![image](https://user-images.githubusercontent.com/30026192/148941795-a7c681c5-980b-4294-a4b3-3df38686f3ff.png)

![image](https://user-images.githubusercontent.com/30026192/148941973-4d54e879-3375-414b-b572-cc90735df978.png)

![image](https://user-images.githubusercontent.com/30026192/148942075-53f488ed-7ea8-4520-a6a8-6822249e26bd.png)



