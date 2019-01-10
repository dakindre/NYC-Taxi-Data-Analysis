# NYC-Taxi-Data-Analysis

## Objective
Reveal insights into the relationship between taxi ride volumes and meteorological data by day. The project examines in particular the number of rides from Manhattan Borough to NYC Airports and their correlation to the levels of precipitation on that given day.

## Approach
Two approaches were taken in order to process the data. The goal of this was to reveal the optimized approach. The two approaches are listed below and a diagram of the AWS architecture is provided. 
```
Local Processing of data using Dask
Cloud Based Processing using AWS
```
![alt text](/images/AWSResults/NYC_Taxi_Data.png)


## Procedure

### AWS
1. Download full data set or subset you wish to use into S3. In the interest of saving money this approach downloaded only yellow taxi for the year of 2018. The schema was consistent across all files therefore several steps could be eliminated upfront with infering schemas and transforming the different dataframes into one consistent set. 

2. Save the Zeppelin notebook in the scripts/AWS folder somewhere in S3

3. Spin up an EMR Cluster Running Spark 2.0 or later with Zeppelin notebook. Depending on the size of the dataset you may want to configure these settings accordingly. For testing purposes the default was fine with 2 core nodes. 

4. Open Zeppelin notebook from S3 and attach it to the cluster. Change the S3 location to point to the directory where your taxi data files are stored and the target directory where you'd like the output to be written to. 

5. Once the job is complete check in S3 to ensure that the parquet write was successful.

6. Go to the Glue dashboard and select crawlers. Create a database if you don't already have one and point the source to the S3 location where the parquet files were written.

7. Run the crawler and ensure a table has been created with the correct schema. 

8. Go to Athena and run a few queries (coming soon) to ensure the data looks correct. 

9. Download the JDBC driver (https://docs.aws.amazon.com/athena/latest/ug/connect-with-jdbc.html) for Athena on your local machine in the Tableau directory. 

10. Here is a good article for setting this up and getting the data loaded into Tableau here (https://www.tableau.com/about/blog/2017/5/connect-your-s3-data-amazon-athena-connector-tableau-103-71105).

11. Actual Report coming soon


### Local
1. Download Green Taxi Data from site (http://www.nyc.gov/html/tlc/html/about/trip_record_data.shtml) onto your local machine. For the example provided it looks only at taxi data from 2013-2014. 

2. Download the script `NYCTaxiDataProcessing.ipynb` from the folder scripts/Local to your machine

3. Open the file in a Jupyter Notebook. Change File Import Location in the script to point to the directory that you saved the above data and run the script. 


#### Local Results
The results were displayed as a series of correlation matricies pertaining to the number of rides in a given day and the amount of percipitation that occured using pearson correlation analysis. They results are as follows for the years 2013-2014 only.

```
Overall Correlation coefficient: 0.063061
Winter Correlation coefficient: 0.045252
Summer Correlation coefficient: 0.08412
```

#### Analysis
The results tell us that there is a very insignificant linear relationship between the amount of rainfall and the number of rides in a given day. The summer value is nearly twice that of winter but still negligible
