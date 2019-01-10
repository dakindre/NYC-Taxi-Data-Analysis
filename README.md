# NYC-Taxi-Data-Analysis

## Objective
Reveal insights into the relationship between taxi ride volumes and meteorological data by day. The project examines in particular the number of rides from Manhattan Borough to NYC Airports and their correlation to the levels of precipitation on that given day.

## Approach
Two approaches were taken in order to process the data. The goal of this was to reveal the optimized approach. The two approaches are listed below and a diagram of the AWS architecture is provided. 
```
Local Processing of data using Dask
Cloud Based Processing using AWS
```
![alt text](/Images/AWS_Data_Flow.png)

### Dependencies
```
Python 3.x

Dask
Geopandas
Numpy
Glob
Shapely
matplotlib
PyArrow
Jupyter
Seaborn
```
### Steps
1. Download Green Taxi Data from here (http://www.nyc.gov/html/tlc/html/about/trip_record_data.shtml)

2. Change File Import Location in file to directory that you saved the above data `NYCTaxiDataProcessing.ipynb`

3. Run Script

### Results
The results were displayed as a series of correlation matricies pertaining to the number of rides in a given day and the amount of percipitation that occured using pearson correlation analysis. They results are as follows for the years 2013-2014 only.

```
Overall Correlation coefficient: 0.063061
Winter Correlation coefficient: 0.045252
Summer Correlation coefficient: 0.08412
```

### Analysis
The results tell us that there is a very insignificant linear relationship between the amount of rainfall and the number of rides in a given day. The summer value is nearly twice that of winter but still negligible
