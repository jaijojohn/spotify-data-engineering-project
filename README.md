# Spotify-data-engineering-project
Introduction.
In this project, we will build an ETL(Extract,Transform,Load) pipeline using the spotify API on AWS. The pipeline retrieve the data from Spotify API, tranform it to a desired format and load it into AWs data store.
For this project, the data was collected from Spotify using Spotify’s API and ‘spotipy’ library. The data is on top 50 songs in India (ranked weekly)

(https://open.spotify.com/playlist/37i9dQZEVXbMWDif5SCBJq)

Services used: S3, IAM, Glue, Lambda, Athena, EventBridge

Process:

Created Spotify developer account to generate API keys.
Assigned roles and policies for the services used thorough IAM.
Created custom python package and generated custom layer to support spotipy library in AWS.
Coded function to extract raw data using Spotify API and ‘spotipy’ python library.
Automated data extraction using lambda triggers and EventBridge for a specified time and store data in ‘raw_data’ folder in S3 bucket.
Executed transform function to convert the raw data into 3 csv files – album, artist, songs in S3
Automated the process of transform function and to copy the transformed files into ‘processed_data’ folder and delete the data from ‘raw_data’ folder.
Utilized Glue crawlers to infer schema and generate tables from the csv files.
Queried the database using Athena to generate insights.
It was a great experience using API to collect data and then transform this raw data into legible data using AWS. This was a fun project as I was able to work with real time data which keeps on updating.

Spotify Developer : https://developer.spotify.com

## Architecture
![Architecture Diagram](achitecture_diagram.png)
