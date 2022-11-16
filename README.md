# Trend Analysis for Ford GoBike Share System
## by Victoria Asefon


## Dataset

Ford GoBike is one of the largest public bicycle sharing system in San Francisco bay ares, US. This document explores a dataset containing Ford GoBike trip data for a period of 1 year between 1 April 2018 to 31 April 2019.

The original dataset can be found here [here](https://s3.amazonaws.com/fordgobike-data/index.html), this is the dataset used in the exploratory-analysis notebook. The total dataset for the 1 year period contained 2,421,723 rows and 16 columns before data wrangling.

In the wrangling phase, I dropped all columns that are not useful in the analysis, replaced NaN values in the age column with the mean age and dropped every other NaN values. I converted the time stamps to datetime format, changed trip durations from seconds to minutes, calculated the members age from the birth year and stored it in a column, and also added a column that shows if the trip is in a workday or a weekend. 

The wrangled dataset, contains 2,409,222 trips and 10 Features. The features are:

- duration_min: Trip Duration in minutes
- start_time: Time the trip started
- end_time: Time the trip ended
- start_station_name: Start Station Name
- end_station_name: End Station Name
- user_type: User Type (Subscriber or Customer, “Subscriber” = Member or “Customer” = Casual)
- member_birth_year: Member Year of Birth
- member_gender: Member Gender
- Age: Members age
- is_weekend: Dummy variable (is it a weekend?)


## Summary of Findings

- Members age ranges from 18 to 70+. There are outliers in the members age most likely due to data entry error, but since it's not the main feature of interest, I did not drop them. Age distribution is right-skewed both on a standard and logarithmic scale. 

- 65.6% of users are above the age of 30. 85.5% of Ford GoBike users are suscribers while the remaining 14.5% are  casual customers.- 

- Trip durations ranges from  1 minute to about 80 minutes. The distribution is right-skewed on a linear scale but when plotted on a logarithmic scale, the distribution was roughly normal.

- There is steady increase in thhe numer of trips up till Jul 2018. Demand reduced slightly in August and September and recovered in October 2018. However, there was a drastic decrease in demand in November and December 2018 and since then, demand has fluctuated monthly. Changes in number of monthly trips tend to be similar for both user types. 

- During the day, the rush hours are between 8-9 am, and 5-6 pm in the evening. Although there are less "customers" than "suscribers" between 5am and 9am. However, from 10am to 4pm, the number of customers increased significantly than suscribers. Demand drops significantly on weekends, and slightly on Monday, Wednesday and Friday.

- Customers demand follow a smoother partern during the week. Subscribers demand drops significantly on weekeds.Peaks days are different for the two groups.

- Most popular start and end stations are not entirely the same.

- Both under 30 and 30+ customers demand demand drops significantly on weekedns with higher demands on workdays.

- Trips durations tend to be longer on weekends compared to workdays; Customers take longer trips than suscribers both on weekends and workdays.


## Key Insights for Presentation

- There are two user groups; **Subscribers** _(members of an annual or a monthly plan)_ and **Customers** _(pay for single trips only)_. **85.5%** of users were **Subscribers**, while **21.6%** were **Customers**.

- Trip durations ranges from  1 minute to about 80 minutes. The distribution is right-skewed on a linear scale but when plotted on a logarithmic scale, the distribution was roughly normal.

- Changes in monthly trips is quiet volatile. There is a drastic decline in trip counts in November and December 2018, and mothly trips keep flunctating afterwards. Changes in number of monthly trips tend to be similar for both user types.

- Monthly growth rate is quiet volatile.

- Ride frequency declines for both under customers under the age of 30 and 30+ customers, demand demand drops significantly on weekends with higher demands on workdays.

- Rush hours are between 8-9am in the morning, and 5-6pm in the evening. Although there are less "customers" than "suscribers" between 5am and 9am. there are more "customers from 10am to 4pm.

- "Customers" tend to have more duration for their trips, and their distribution also have more spread compared to "Subscribers". This means that "Customers" tend to vary their trip durations, while "Subscribers" typically use the service for short trips.

- On average, Trips durations tend to be longer on weekends compared to workdays; Customers take longer trips than suscribers both on weekends and workdays

## Additional information

Download the data [here](https://s3.amazonaws.com/fordgobike-data/index.html)
