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
The primary goal of this project is to use the AWS services such as S3 for data storage and EMR as the processing cluster to process the wikipedia data for two main tasks: to filter out records by  conditions, where 'isRobot': False & 'countryName': “United States” and to aggregrate the data by the channel.
This information can be used for various analyses and research purposes related to Wikipedia, such as studying patterns in the types of edits that are made, examining the behavior of different types of editors, or tracking the evolution of particular articles over time.

## Datapipeline 













