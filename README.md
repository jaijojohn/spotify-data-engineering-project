# Spotify-data-engineering-project
Introduction.
In this project, we will build an ETL(Extract,Transform,Load) pipeline using the spotify API on AWS. The pipeline retrieve the data from Spotify API, tranform it to a desired format and load it into AWs data store.
For this project, the data was collected from Spotify using Spotify’s API and ‘spotipy’ library. The data is on top 50 songs in India (ranked weekly)

(https://open.spotify.com/playlist/37i9dQZEVXbMWDif5SCBJq)

AWS Services used:
Lamda
S3 bucket
Cloudwatch
Glue
Athena
The pipeline is divided into 3 parts:
Extract
Transform
Load

🔶 Extract

Data Extraction from Spotify API using Python on local using Spotipy.
Using AWS Lambda to deploy the extraction function - spotify_api_data_extract.
Applied Cloud Watch to automate and run Triggers every 1 min.
Stored the extracted raw data in S3 Bucket in to_processed folder.

🔶 Transform

Added S3 triggers when new data comes in bucket, whenever new data comes, it will 2nd function for further transformation.
Applied Data Transformation using AWS Lambda on function - spotify_transformation_load_function
Storing the transformed data in S3 Bucket in different folders(Album, Artist, Song) and also moves data from to_processed to processed folder.

🔶 Load

Used Glue Crawler to infer schemas whenever there is new data in S3 Bucket.
Create AWS Glue Data Catalog to manage the Metadata Repository.
Use Amazon Athena to query and analyse the final dataset for desired information.

## Architecture
![Architecture Diagram](achitecture_diagram.png)
