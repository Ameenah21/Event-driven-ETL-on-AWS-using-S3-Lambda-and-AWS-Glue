# Event-driven-ETL-on-AWS-using-S3-Lambda-and-AWS-Glue
# Introduction
A company wants to launch a new data driven campaign on Youtube and wants to understand the factors that determine how popular a Youtube video will get and characteristics of trending youtube videos. I will be extracting the data on trending videos using this scraper [here](https://github.com/Ameenah21/Trending-YouTube-Scraper) and build a pipeline to clean and format the data so that the data analytics team can query the data and answer business questions effectively.
# Architecture diagram
![Architecture](Event-driven-ETL-on-AWS-using-S3-Lambda-and-AWS-Glue/images/ETL on AWS.png)
# About the Data
The script outputs the project in two folders by countries. A json format containing the metadata about the video and a csv file containing the list of the trending videos in each countryl
# Running the Project
- Create an S3 Object to store the Data.
- A lambda function to extract the json data in the form that can be queried by athena.
- Create a crawler to crawl the output and create catalogue from the lambda function.
- Create and run AWS Glue job to update data schema, partition the data and store output as parquet file in cleaned S3 bucket
- Create a crawler to crawl the output and create catalogue from the lambda function. 
-  Create and run AWS Glue job join the data from both tables created in the catalogues. Store output in the analytics buckets.
This tep is necessary beacuse to query entire data will require joining both tables each time

# IAM Roles and Permissions
You will create IAM roles for Lambda and Glue with read and write permisions for s3 and glue
