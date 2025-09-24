A brief summary of the case study:
- Cyclistic is a bike-share program that features more than 5,800 bicycles and 600 docking stations.
- My task is to identify how annual members (vs casual riders) differ in the use of the Cyclistic program.
- Key takeaways are: 
  1) Members take shorter, and more frequent rides during the weekday (Mond - Fri). Members tipically use the Cyclistic bikes to commute.
  2) Casual users take longer, and less frequent rides during the weekend. Casual users tipically use the Cyclistic bikes as leisure or tourism.
  3) This showcases an opportunity to target casual riders to start using more Cyclistic bikes during the weekday or other times of day. Target them with promotions for leisure-to-commuter conversion.
- My recommendations are:
  1) For casual riders, highlight the convenience for commuting (e.g., unlimited rides, saves money).
  2) Target digital ads/social media for tourists and casual riders, showcasing the true value of annual plans for more frequent outgoing leisure rides (e.g., health benefits, spend time with family).
  3) Create discounted annual memberships for tourists (possibly during the summer) who take more multiple long weekend rides.

Since I have all the code in the other file, here I'll leave only the text explaining more about my thought process and analyses. 
## Ask

* Business Task: Identify how annual members and casual riders use Cyclistic differently.
* Goal: Design marketing strategies aimed at converting casual riders into annual members.
* Why this matters: Annual members are more profitable than casual riders.
* Question: How do annual members and casual riders use Cyclistic bikes differently?
* Stakeholders: Lily Moreno (Director of Marketing), Marketing Analytics Team, and Cyclistic Executive Team.

## Prepare

* Data Source: Public Divvy bike-share datasets (2019 Q1 and 2020 Q1).
* Format of File: CSVs with ride-level details (e.g., start time, end time, type of bike, user type, etc)
* Bias & Credibility (ROCCC framework): The datasets are Reliable, Original, Comprehensive, Current, and Cited.
* Limitations: Due to memory limit, I am only able to use 2019 and 2020 Q1 data. I'm also unable to get access to all information due to data-privacy issues (e.g., credit card numbers to determine if casual riders live in a Cyclistic service area of if they have purchased multiple single passes).
The data has been made available by Motivate International Inc. under this [license](https://divvybikes.com/data-license-agreement).

## Process

* 1. I installed (and pulled) lubridate and tidyverse for wrangling and date-time manipulation

* 2. Loaded both datasets 2019 and 2020 Q1

* 3. Inspected the data (e.g., check datasets structure, column names, missing values, consistency of data, etc). 

* 4. The two datasets are using different naming conventions (e.g., trip_id in q1_2019 vs ride_id in q1_2020) so it's important to standardize column names in order to combine them.

* 5. Before merging, we should check and convert the data types to their proper formats. 

* 6. When both datasets' schemas match, we can merge them.

* 7. We can then start creating new time and date-based dimensions.

* 8. Now that we have new dimensions it's time to eliminate bad data, i.e., records that are likely typos/errors (e.g., bike rides with 1m or less or longer than 24h). Missing data on station's name was also eliminated (only whole available trips were considered).

* 9. In order to verify if your data cleaning was successful, run again the summary function specifically for the ride_length variable.

* 10. Before moving on to data analysis, we should do a quick sanity check to ensure everything is in order to move to the next step. For that, I am going to do a histogram of the ride lengths that will allow me to see the most common ride lengths, outliers, number of rides at either extreme, gaps in the data. 

* 11. Lastly, don't forget to keep a clean version for data analysis. Save your work!

## Analyze

A reminder of the business task at hands: How do annual members and casual riders use Cyclistic bikes differently?

Key variables crucial to analyze are ride lengths, frequency, timing, station usability, and deeper insights, seasonality and geospatial trends will be further explored.

We should start with the basics - descriptive statistics.

Next, I am going to look into monthly, weekly, daily, and hourly patterns.

Let's also look at station popularity.

For a more advanced look into the rides we can create clusters and divide trips into shorter rides, during rush hour (commuting; cluster 1), rides during the day (likely errands; cluster 2), and longer rides, during the weekends (leisure; cluster 3).

## Share

Finishing the analysis part, we should focus on building a compelling narrative around data using storytelling.

My audience is the Cyclistic executive team which is detail_oriented and non-technical.

The key message to build around a narrative is that members take shorter, frequent and more weekday trips (also known as commuters) and the casual rides take longer, less frequent and more weekend rides (also known as leisure users).

The volume of rides by user type showing how members take far more trips than casual users.

Casual rides skew much longer than members which peak quite rapidly (commuting vs leisure rides).

Members' number of rides peak during the week from Monday to Friday (commuting) and diminish during the weekend. Casual rides showcase the opposite pattern, peaking during the weekend (leisure) and diminishing during the week.

Members hourly trends showcase a peak at 8h and then at 17h (going to and coming off work) whereas casual riders usage trend midday.

Members most popular starting stations are streets, boulevards, and avenues - more urban/business/downtown areas.
Casuals most popular starting stations are lakes, parks, and other attractions - more tourist attractions.

When are the stations most occupied during the day? Members stress the system during rush hours and casual users more during the afternoons and weekends.

* The key takeaways are:
- Members take shorter, and more frequent rides during the weekday (Mond - Fri) and tipically use the Cyclistic bikes to commute (peaking hours ate at 8h and 17h).
- Casual rides take longer, are less frequent and more on weekends (Sat - Sun). Casuals tipically use the Cyclistic bikes leisurely, with peak usage during the day.
- Members most popular starting stations are more urban/business/downtown areas whereas casuals' most popular starting stations are more tourist attractions.
- This showcases an opportunity to target casual riders to start using more Cyclistic bikes during the weekday or other times of day. Target them with promotions for leisure-to-commuter conversion.

## Act

Here's my 3 actionable recommendations:
- For casual riders, highlight the convenience for commuting (e.g., unlimited rides, saves money)
- Target digital ads/social media for tourists and casual riders, showcasing the true value of annual plans for more frequent outgoing leisure rides (e.g., health benefits, spend time with family)
- Create discounted annual memberships for tourists (possibly during the summer) who take more multiple long weekend rides.
