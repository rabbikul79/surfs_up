# surfs_up
## Overview of the analysis:
The purpose of this project is to analyze weather data using pandas data frame from sqlite database file for a prospective business. The analysis contained the temperature trend for month of June and December over the course of 7 years of data.

## Results:
The analysis displays the target location - Oahu’s June & December temperature trend below: 

June:

![June_Data](https://user-images.githubusercontent.com/85530486/132963065-af8c85fd-6890-486d-84f2-2029572f77f9.png)

December:

![December_Data](https://user-images.githubusercontent.com/85530486/132963078-0a7e9135-4f34-4565-9703-96119097bec5.png)

The key differences for the 2 months temperature are listed below:
-	Mean: The average temperature for June is 75F Dec is 71F
-	Max: The Maximum temperature for June is 85F Dec is 83F
-	Min: The Maximum temperature for June is 64F Dec is 56F

## Analysis:
By analyzing the year around temperature data and reading through the focus month of June and December it can be said that the weather is temperature all through the year. Which will be very suitable for the proposed Ice-cream shop. For further decision other factor like precipitation data should be analyzed. 
The following query can be used for the precipitation analysis:

results = session.query(Measurement.date, Measurement.prcp).filter(Measurement.date >= prev_year).all()

Also, the station with the highest number of observations should be considered when the analysis of temperature and precipitation is calculated.  
The following query can be used for the station analysis:

session.query(func.min(Measurement.tobs), func.max(Measurement.tobs), func.avg(Measurement.tobs)).\
filter(Measurement.station == 'USC00519281').all()
