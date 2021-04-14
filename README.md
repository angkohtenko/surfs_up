# Surf's Up Analysis
## Overview of the analysis
The goal of the project is to analyze weather data which is stored in a SQLite database, explore whether temperature and precipitation allow to surf comfortably, present the result in Flask application. 

To complete the project, I’ve used Python, Jupyter Notebook with Pandas, Matplotlib, SQLAlchemy and Flask libraries.

## Results
First of all, I’ve created engine to connect the SQLite database and created classes that mapped to each table. There are 2 tables in the database:
-	Measurements made by stations (date, tobs and precipitation)
-	List of stations with their coordinates, elevation and name.

During exploratory analysis I retrieved precipitation by date and built the bar chart.

![](https://github.com/angkohtenko/surfs_up/blob/main/Resources/precipitation_bar_chart.png)

Also, I calculated summary statistics for temperature recorded by the most active station:

![](https://github.com/angkohtenko/surfs_up/blob/main/Resources/summary_statistics_temperature%20.png)

Then I've created flask app and made separate routes to show:
-	precipitation
-	stations
-	temperature
-	min, avg, max temperatures for the certain period of time

![](https://github.com/angkohtenko/surfs_up/blob/main/Resources/flask.png)

To compare temperature for two months June and December, I stored data to the dataframes and calculated summary statistics.

![](https://github.com/angkohtenko/surfs_up/blob/main/Resources/temp_summ_June.png) ![](https://github.com/angkohtenko/surfs_up/blob/main/Resources/temp_summ_Dec.png)

-	There are more measurements in June than in December (1700 vs 1517)
-	Average temperature in December 3.9 degrees lower than in June (71˚F vs 74.9˚F). 
-	Temperature in December is a little bit volatile than in June (std 3.74 vs 3.25)
-	Some cold days happened in December (min 56˚F), but most of the time temperature is between 69˚F and 74˚F.

## Summary
Although cold days happened in December, the temperature in June and December are pretty similar and looks comfortable for surfing.

To extend the analysis I’ve made a similar summary statistics for precipitation. The precipitation in December a little bit higher (mean 0.21 vs 0.13) and volatile (std 0.54 vs 0.33). 

![](https://github.com/angkohtenko/surfs_up/blob/main/Resources/precip_summary.png)

Also, I calculated total precipitation in June and December for every year. So, it’s easy to see that precipitation in December tends to be 3-5 mm more than in June. December in 2010 was truly rainy month (105.59 mm).

![](https://github.com/angkohtenko/surfs_up/blob/main/Resources/precip_total_level.png)

But how often does it rain?  I counted all precipitation measurements in June and December if it’s more than 1 mm. 

![](https://github.com/angkohtenko/surfs_up/blob/main/Resources/precip_frequency.png)

Rains happen more often in December than in June. That can be a problem for surfing in December.
