#Surfs Up Analysis

## Overview of Oahu Temperature Analysis
To open a Surf n' Shake shop in Oahu requires an investor W. Avy.
This shop will sell both ice cream and surf boards year-round.
To determine if this is a sustainable business plan requires analysis of temperature data on the island.
By using Python, Pandas functions and SQLAlchemy I will generate summary statistics for temperatures in June and December.
This analysis will dictate if W. Avy will invest in the company.

### Purpose
The SQLite file [hawaii.sqlite](hawaii.sqlite) is the database that contains the necessary data to run queries.
The file [SurfsUp_Challenge.ipynb](SurfsUp_Challenge.ipynb) will contain the code to generate the summary statistics.
First a query was written to retrieve the applicable month of temperatures from the date column of the Measurement table.
Next those temperatures were added to a list.
Then the list of temperatures was converted to a Pandas DataFrame.
Finally the summary statistics were generated for the DataFrame.

## Temperature Results
### Three Major Points:
- Mean Temperature
	- In June the average temperature is 74.94 degrees.
	- In December the average temperature is 71.04 degrees.
	- There is not a significant difference in the average temperatures between the two months.
	- The code used to filter for the month of June is 'june_temps = session.query(Measurement).filter(extract("month", Measurement.date) == 6)'.
	- That code was refactored for the month of December 'dec_temps = session.query(Measurement).filter(extract("month", Measurement.date) == 12)'.

- Standard Deviation
	- The standard deviation measures the dispersion of a dataset relative to its mean.
	- A higher standard deviation indicates larger variability within a dataset.
	- In June the standard deviation is 3.26.
	- In December the standard deviation is 3.75.
	- In December it is more likely that the temperature will be further from the mean of 71.04 degrees.

- Minimum Temperature
	- In June the minimum temperature is 64.00 degrees.
	- In December the minimum temperature is 56.00 degrees.
	- The difference in minimum temperatures is significant.

The code used to generate the summary statistics is 'df_june.describe()' for June and 'df_dec.describe()' for December.
The summary statistics are in [June_Summary_Statistics.PNG](June_Summary_Statistics.PNG) and [December_Summary_Statistics.PNG](December_Summary_Statistics.PNG).

## Temperature Analysis Summary

- Summary of the temperature analysis for June and December

In December it can be significantly colder than in June.
The minimum temperature in June is 64.00 degrees and in December it is 56.00 degrees which is 8 degrees colder.
Customers will be less likely to go surfing or eat ice cream on cold days.
In December 25% of the recorded temperatures are below 69.00 degrees.
Half the days in December are still above 71.00 which is a reasonable temperature for surfing and eating ice cream.

- Two additional queries that could be performed to gather more weather data for June and December?

Precipitation and humidity are also important factors that impact whether people would be out surfing and eating ice cream.
Performing queries on precipitation and humidity would be beneficial when evaluating the sustainability of the Surf n' Shake shop.
Weather patterns can vary by location on the island. 
Performing the same temperature analysis on the closest weather station to the purposed store location would also provide valuable information.


