# WEB-API-Spotify-Data-ETL-Pipeline-using-Snowflake-AWS-S3-Lambda-Python-SQL
The Spotify Data Pipeline project is an ETL (Extract, Transform, Load) solution designed to automate the extraction of top tracks and metadata from the Spotify Web API, transform the data, and load it into AWS S3 and auto ingest to snowflake for further analytics.

Key Features:
Data Extraction: The pipeline fetches the top tracks of a given Spotify artist using the Spotify Web API. This includes retrieving song details, album metadata, and artist information.

Data Transformation: Once the data is fetched from the Spotify API, it is processed using the Pandas library in Python to organize the raw data into three categories: Songs, Albums, and Artists.

Data Storage: Transformed data is stored in AWS S3, categorized into a structured folder format (raw_data/to_processed/ and transformed_data/) to facilitate easy integration with downstream systems.

AWS Lambda Automation: The entire pipeline runs on AWS Lambda, where custom Lambda layers are used to include necessary external libraries (such as Pandas, NumPy, and Requests). The Lambda functions are triggered to run every minute, collecting and processing fresh data from the Spotify API.

Snowflake Integration: The project leverages Snowflake to enable advanced analytics. Data in S3 is continuously loaded into Snowflake using Snowpipe for real-time data ingestion. Snowflake tables are created for storing the transformed artist, album, and song data.
