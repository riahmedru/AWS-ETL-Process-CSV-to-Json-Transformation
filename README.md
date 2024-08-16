# AWS ETL Process: CSV to Parquet Transformation

## Introduction
##### This project showcases a simple ETL process using AWS Glue to convert CSV data into a Parquet format. The transformation involves reading data from an S3 bucket, applying schema transformations using AWS Glue Catalog, and writing the transformed data back to S3.

## Prerequisites
##### AWS Account: Access to AWS services.
##### IAM Role: An AWS IAM role with permissions to use AWS Glue, S3, and related services.
##### S3 Bucket: An S3 bucket to store the input CSV and output Parquet files.
##### AWS Glue Service: Permissions to create jobs and manage Glue Catalog.

## Project Architechture
![Untitled Diagram drawio](https://github.com/user-attachments/assets/699a7966-3809-451d-bfd9-4946dd8fab83)

## AWS Services Used
##### AWS Glue: For running ETL jobs.
##### AWS S3: For storing the CSV and Parquet files.
##### AWS Glue Catalog: For schema management and transformations.

## Setup Instructions
### Step 1: 
##### Create a S3 Bucket
<img width="213" alt="Screenshot_1" src="https://github.com/user-attachments/assets/878e2d35-674a-4cd1-8572-0868e36c75c0">

##### Create folder "datastore" for input data and "target-datastore" output data.
<img width="289" alt="Screenshot_12" src="https://github.com/user-attachments/assets/1d5b1dd6-3dba-4dee-9a00-308b381cca4b">
 
##### Upload CSV file to datastore folder
<img width="287" alt="Screenshot_2" src="https://github.com/user-attachments/assets/4f505aa4-d7df-4927-956a-eabfdcd95c59">

### Step 2: 
##### Configure the AWS Glue Catalog
##### Create a Database 
<img width="281" alt="Screenshot_3" src="https://github.com/user-attachments/assets/25ee688d-2c52-48c8-b8b4-36d6a009fb67">

##### Create a table 
<img width="743" alt="Screenshot_4" src="https://github.com/user-attachments/assets/7dab8f3c-51de-4c2f-8b52-86470881b4d8">

##### Create a crawler and add the CSV file as S3 datasource
<img width="324" alt="Screenshot_5" src="https://github.com/user-attachments/assets/f4f28335-e432-435f-b372-60e3ba2b0c16">

##### Select the IAM role if you did't have create any IAM Role then create a an IAM role with ( AmazonS3FullAccess, AWSGlueConsoleFullAccess, CloudWatchEventsFullAccess)
<img width="538" alt="Screenshot_6" src="https://github.com/user-attachments/assets/0983be36-7ac4-4500-bd3f-e53824f5be62">

##### Select the S3 Bucket as target database
<img width="528" alt="Screenshot_7" src="https://github.com/user-attachments/assets/531734ff-6d89-489c-a96e-1166cacfc581">

##### And then Run the Crawler
<img width="738" alt="Screenshot_8" src="https://github.com/user-attachments/assets/7182fe23-dd09-4b9f-9ba3-132cbc6bda64">

### Step 3
##### ETL Job Process
##### Extract: The CSV file is extracted from the specified S3 bucket.
##### Transform: Schema transformations are applied using AWS Glue Catalog.
##### Load: The transformed data is saved back to the S3 bucket in Parquet format.

<img width="277" alt="Screenshot_9" src="https://github.com/user-attachments/assets/e7443ce1-6986-4511-b704-0fd0624bba7c">

##### Start the Glue Job:
##### Run the job from the AWS Glue Console.
##### Monitor the job's progress in the console or CloudWatch.
##### Verify Output:

##### After the job completes, check the S3 bucket for the Parquet file.
<img width="485" alt="Screenshot_10" src="https://github.com/user-attachments/assets/a0348fde-f64d-48f0-bf5d-c21e641cac2d">




