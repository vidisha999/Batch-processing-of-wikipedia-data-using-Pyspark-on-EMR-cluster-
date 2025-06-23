# Batch Processing of large data using PySpark on AWS EMR

## Description 
This project focuses on batch processing Wikipedia data to analyze large volumes of data and gain insights into its content and structure. Using AWS EMR (Elastic MapReduce) with PySpark, the process preprocess Wikipedia articles and employs techniques like text analysis, sentiment analysis, and statistical analysis. These methods help identify patterns and trends in the articles, ultimately aiding in training machine learning models.

## Background 
Data processing can be classified in to multiple types depending on the type and volume of the data & complexity and speed of the processing. Batch processing the technique of processing large volumes of data grouped together at periodic intervals of time allowing efficient processing of data in a consistent manner while reducing errors and risk of data loss or corruption by processing data in a controlled and consistent manner.It also  supports historical reporting that helps in tracking the trends and patterns in the data. 

The batch processing involves several key steps: collecting data from various sources and storing it temporarily, validating the data to meet required standards, transforming it into a suitable format, processing it with algorithms, and finally, storing the results in a designated location for further analysis or processing.So, batch processing technique is used to efficiently process the Wikipedia data used for analysis in this project which comes in regular data dumps that contain entire contents of the site. 

## Data
The wikipedia dataset used in this project is in JSON format and it contains wikipedia edits that were made on September 12,2015. 
The [dataset](Data/wikiticker-2015-09-12-sampled.json) includes information about each edit, such as the title of the editted article, the
username or IP address of the editor, the timestamp of the edit, and the text of the edit itself. 

## Goal 
The primary goal of this project is to use the AWS services such as S3 for data storage and EMR as the processing cluster to process the wikipedia data for two main tasks: to filter out records by  conditions, where `isRobot`: False & `countryName`: “United States” and to aggregrate the data by the channel.
This information can be used for various analyses and research purposes related to Wikipedia, such as studying patterns in the types of edits that are made, examining the behavior of different types of editors, or tracking the evolution of particular articles over time.

## Datapipeline 

### 1. Storage of sampled data in AWS S3 bucket 
A AWS S3 bucket is created with two folders: `input-dat`a for storing raw sampled data and `output-data` for storing processed data.

### 2. Set up AWS EMR cluster 

- Amazon EMR:

  Amazon EMR( Elastic Map Reduce) is used as the processing cluster in this project. Amazon EMR is a fully-managed big data processing service from AWS that simplifies handling large data volumes using frameworks like Apache Hadoop, Apache Spark, and Presto. It automates the provisioning, scaling, and management of clusters running these frameworks. EMR offers a user-friendly web interface, command-line tools, and APIs for cluster management. It's key features include being fully managed, scalablility with workload demands, being flexible with support for various big data tools, having a pay-as-you-go model and spot instances, and integrated with other AWS services like S3, DynamoDB, and Redshift for seamless data movement.

 - Creating EC2 key pair:
   
   In order to ecurely access the EC2 instances that will be created when creating the EMR cluser, a key pair should be created and downloaded as a .pem file. The key pair is used to authenticate the SSH (Secure Shell) connections to EC2 instances, and it's important to keep it secure and protected.

- Configuring the cluster :
  
  When creating the EMR cluster, the **Spark application** bundle is installed, including **Hadoop** and **Spark** for big data processing, **Hive** for data warehousing and SQL-based querying, and **Zeppelin** as a collaborative notebook for data analytics and visualization using SQL and Python. The network and security settings are configured to allow SSH access to the primary cluster node using an SSH key pair.IAM roles for the cluster should be granted permissions for S3FullAccess and EC2FullAccess policies, as AWS S3 will be used for storage and EC2 for computing and processing.







