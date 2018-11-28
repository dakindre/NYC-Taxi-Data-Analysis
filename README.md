# NYC-Taxi-Data-Analysis
Analysis of NYC Green Taxi and Meteorological Data Analysis to find correlation between percipitation and ride volume

The analysis is broken out by overall correlation and seasonal

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
The results were displayed as a series of correlation matricies pertaining to the number of rides in a given day and the amount of percipitation that occured using pearson correlation analysis. They results are as follows

```
Overall Correlation coefficient: 0.063061
Winter Correlation coefficient: 0.045252
Summer Correlation coefficient: 0.08412
```

### Analysis
The results tell us that there is a very insignificant linear relationship between the amount of rainfall and the number of rides in a given day. The summer value is nearly twice that of winter but still negligible
