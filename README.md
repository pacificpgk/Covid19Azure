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
            <td rowspan=3>ds_ecdc_raw_http</td>
            <td>cases_deaths.csv</td>
            <td rowspan=5>ls_dl_covid19r
             eportingdtlk</td>
            <td rowspan=3>ds_ecdc_raw_csv_dl</td>
            <td>cases_deaths.csv</td>
            <td>Github Site</td>
        </tr>
        <tr>
            <td>hospital_admissions.csv</td>
            <td>hospital_admissions.csv</td>
            <td>Github Site</td>
        </tr>
        <tr>
            <td>testing.csv</td>
            <td>testing.csv</td>
            <td>Downloaded File</td>
        </tr>
        <tr>
            <td rowspan=2>NA</td>
            <td rowspan=2>NA</td>         
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

# [Linked Service](https://github.com/pacificpgk/Covid19Azure/blob/main/Linked_Service.md)

# [Ingest Population Data](https://github.com/pacificpgk/Covid19Azure/blob/main/Data_Ingestion.md)

# [Ingest ECDC Data](https://github.com/pacificpgk/Covid19Azure/blob/main/ECDC_Data.md)
