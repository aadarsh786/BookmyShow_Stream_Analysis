# BookmyShow_Stream_Analysis


  <br>
  <br>
   

## PROJECT OVERVIEW

The project automates the process of fetching news articles related to Tesla from the News API, processing this data, and storing it in Google Cloud Storage (GCS) as a Parquet file. This file is later moved to a Snowflake data warehouse for analysis. The project uses Airflow for orchestration, ensuring the data ingestion and processing occur periodically and smoothly.

 <br>




### PROJECT EXPLANATION :-  


#### Data Fetching: 
The pipeline retrieves recent news articles related to Tesla using the News API. Each article’s data, including author, title, source, timestamp, and content, is processed and stored in a DataFrame.

#### Data Processing and Storage in GCS:

After processing, the data is saved locally as a Parquet file.
The file is then uploaded to a specified location in a Google Cloud Storage (GCS) bucket.

#### Data Loading to Snowflake:

In Snowflake, a destination table is created if it doesn’t already exist.
The Parquet file from the GCS bucket is copied into this destination table for analysis.

#### Airflow Orchestration:
Airflow manages and schedules the pipeline, triggering data fetching, processing, storage, and loading operations daily.

  
  
  
   
   
      


     

  










<br>
<br>
<br>

## ARCHITECTURE DIAGRAM :-

![Project Architecture](BookmyShow_Architecture.png)  










<br>
<br>
<br>

## TECHNOLOGY USED :-

<h3>Azure Event Hub:</h3>

Orchestrates the entire workflow by defining tasks that automate fetching, processing, saving, and uploading data.

<h3>Azure Stream Analytics Job:</h3>

Used for scripting the logic for data fetching, processing, and file handling.

<h3>Azure Synapse:</h3>

Provides news data based on search queries. It offers access to various news articles, including their metadata, such as title, author, and content.

<h3>Python:</h3>

A Python library used to handle the structured data (articles) in a DataFrame, process it, and save it to disk in a columnar format (Parquet).

<h3>Pyspark:</h3>

A cloud storage service where the processed Parquet files are stored temporarily before being ingested into Snowflake.



<br>
<br>
<br>



## Script Files  :-
* <h3>Python-File:
[Python-code-snippet](prac2.py) - Contains the core functions for fetching and processing data, and uploading it to GCS. </h3>
 </br>
 </br>
 
 * <h3>Airflow-Dag :
  [Airflow-Dag-file](airflowjobprac.py) -  Defines the workflow and schedules the data pipeline tasks.  </h3>
  

  </br>
  </br>
  
## Resulted output :- 

<h3>The output is stored in Parquet format with unique filenames that reflect the datetime of each run.</h3>

 - <h3>Output_link_1 :</h3>
  [Result1](https://github.com/aadarsh786/News-Data-Analysis-Project/blob/main/SNOWFLAKE_PROJECT_PARQUET_FILES_run_20241105064621.parquet)

 - <h3>Output_link_2 :</h3>
  [Result2](https://github.com/aadarsh786/News-Data-Analysis-Project/blob/main/SNOWFLAKE_PROJECT_PARQUET_FILES_run_20241105064940.parquet)












