# Tableau-CitiBike

![citi-bike](Images/citi-bike-station-bikes.jpg)

Link to [citibike Analysis](https://public.tableau.com/profile/sara7063#!/vizhome/CitiBike_Analysis_16131005084360/citibikeAnalysis)

## Table of contents
* [Technologies](#technologies)
* [Objective](#objective)
* [Data Cleaning](#data-cleaning)
* [Data Aggregation](#data-aggregation)
* [Visualizations](#visualizations)
* [Analysis](#analysis)
* [Tableau Story](#tableau-story)
* [Resources](#resources)
* [Contact](#contact)

## Technologies
* [Tableau](https://www.tableau.com/) 
* Pandas

## Objective
citibike Rider and Station Analysis: 2019 vs 2020 

citibike Ridership: Pre- COVID-19 vs. During-COVID-19 
  
*Has the customer base changed? 
*Have the top station locations changed due to WFH lifestyle? 
*Have the trip totals gone up or down due to COVID-19 pandemic? 
  
The following visualizations will illustrate citibike ridership data from August, September, October 2019 as compared to August, September, October 2020. 
  
These months were selected because the weather is nice, so bike riding is one of the preferred ideal mode of transportation. The data is representative of Tourism in August as well as student populations in September.

## Data Cleaning

I collected the data from [Citi Bike Data](https://www.citibikenyc.com/system-data).  I used Citi Bike trip history data from August, September and October of 2019 and August, September, and October of 2020. The files were very large and included trip and rider data from every station for the entire month. I used `pandas` in a jupyter notebook to clean the data. To clean it, I used the `concat` function to combine all the date into one `dataframe`. 

![concat](Images/concat.JPG)

Then I separated out year and month from the start date column. This helped me clearly visualize the date in my tableau story. 

![clean year](Images/clean_year.JPG)

![clean month](Images/clean_month.JPG)

Rider gender was represented by number values in the original data set so I assigned ‘male’ and female’ values in place of the numbers to be more meaningful. 

![gender](Image/gender_clean.JPG)

To display age in my visualizations, I calculated the rider age by subtracting the birth year given in the data by the trip year. I created a new column for rider age.

![age](Image/clean_age.JPG)

## Data Aggregation

The date from citibike was exceptionally large and was too big to use in Tableau in its original form. I created different aggregations of the data sets to make smaller data frames that would be ok to use in Tableau Public. The smaller data frames also made visualizations easier to display. 

To create the total citibike trips per year, I used the `.groupby` function to group the data by Trip Year and Trip month and count the total trips. 

` month_df = clean_df3.groupby(['Trip Year','Trip Month']).count() `

![Total Data](Images/total_data.JPG)

To create the user data frame, I used the `.groupby` function and grouped the data by Trip Year, Trip Month, Rider Gender, Rider Age, and User Type. I added ` .count() ` to calculate the sum of each group. 

` user_df1 = user_df.groupby(["Trip Year", "Trip Month", 'Rider Gender', 'Rider Age', 'User Type']).count() `

![user df](Images/agg_user.JPG)

## Visualizations 



## Analysis

After reviewing the visualizations, I concluded the following:

![conclusion](Images/conclusion.JPG)

## Tableau Story

Below is the final Tableau Story. You can also view it on the Tableau Public site- [citibike Analysis](https://public.tableau.com/profile/sara7063#!/vizhome/CitiBike_Analysis_16131005084360/citibikeAnalysis)


![intro](Images/intro.JPG)

![rider age](Images/rider_age.JPG)

![rider type](Images/rider_subscription.JPG)

![start stations](Images/start_station_trips.JPG)

![top 10 start](Images/top_10_start_bub.JPG)

![top 10 start map](Images/top_10_start_map.JPG)

![end stations](Images/end_station_trip.JPG)

![top 10 end](Images/top_10_end_bub.JPG)

![top 10 end map](Images/top_10_end_map.JPG)

![conclusion](Images/conculsion.JPG)

## Resources

CitiBike Data Sources:

[201907-citibike-tripdata.csv](https://s3.amazonaws.com/tripdata/201907-citibike-tripdata.csv.zip)

[201908-citibike-tripdata.csv](https://s3.amazonaws.com/tripdata/201908-citibike-tripdata.csv.zip)

[201910-citibike-tripdata.csv](https://s3.amazonaws.com/tripdata/201910-citibike-tripdata.csv.zip)

[202008-citibike-tripdata.csv](https://s3.amazonaws.com/tripdata/202008-citibike-tripdata.csv.zip)

[202009-citibike-tripdata.csv](https://s3.amazonaws.com/tripdata/202009-citibike-tripdata.csv.zip)

[202010-citibike-tripdata.csv](https://s3.amazonaws.com/tripdata/202010-citibike-tripdata.csv.zip)


## Contact

[Sara Simoes](https://github.com/Ssimoes48)
