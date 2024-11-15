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

<h3>SQL:</h3>

Orchestrates the entire workflow by defining tasks that automate fetching, processing, saving, and uploading data.


<h3>Python:</h3>

Used for scripting the logic for data fetching, processing, and file handling.

<h3>Azure Event Hub:</h3> 


Provides news data based on search queries. It offers access to various news articles, including their metadata, such as title, author, and content.


<h3>Azure Synapse:</h3>

A Python library used to handle the structured data (articles) in a DataFrame, process it, and save it to disk in a columnar format (Parquet).


<h3>Azure Stream Analytics job:</h3>

A cloud storage service where the processed Parquet files are stored temporarily before being ingested into Snowflake.



<br>
<br>
<br>



## Script Files  :-
* <h3>Python-Files: </h3>
  <h4>It will generate bookings mock data:-</h4>
- [Python-code-snippet](mock_bookings.py)

  </br>
  <h4>It will generate payments mock data:-</h4>
- [Python-code-snippet](mock_payments.py) - 


 </br>
 </br>
 
  <h3>Sql snippet:</h3>
   - <h4>Stream Analytics job Query:</h4>
  https://github.com/aadarsh786/BookmyShow_Stream_Analysis/blob/main/stream_analytics_job_query.sql
   </br>
   - <h4>Result Output will store in this table.:</h4>
  https://github.com/aadarsh786/BookmyShow_Stream_Analysis/blob/main/synapse_create_table.sql
  
  
  

  </br>
  </br>

  







