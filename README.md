# Introduction
Hey! My names Bobby and Im currently enrolled in the last chapter on Coursera for "Google Data Analytics Professional Certificate", This is the start of my porfolio on Cyclistic Case Study You can contact me at "CHIENG@LIVE.CA for any questions"

# Prepare
Data:
[Click Here to download the previous 12 months of the Cyclistic trip data ](https://divvy-tripdata.s3.amazonaws.com/index.html)

The data used for this analysis was provided by Cyclistic and consists of trip records from Google Data Analytics Professional Certificate course. The data was preprocessed to remove any missing values and ensure consistency in formatting. Filling missing values, removed duplicates, and reformatting;alining using R stuidio.


# Proccess
To sum up my results, I have found a few concerns:

1. rider_id ✔️ 
This row corresponds to each rider based on their ID which also means this is the primary key. It contains exactly 16 characters no nulls or missing values could be found. 

2. rideable_type: ✔️ 
the data contains 3 types of bikes: classic, docked, and electric bikes; however, as specified by the data collection team, ‘docked bike’ is the old name for ‘classic bike’. So we must change any occurrence of ‘docked bike’ to ‘classic bike’ in R Studio.




>library(dplyr)

>cleaned_data <- cleaned_data %>% 
  mutate(rideable_type = ifelse(rideable_type == "docked bike", "classic bike", rideable_type))



3. The "started_at" and "ended_at" columns In the dataset indicate when bike trips began and ended. However, there are quite a few trips that lasted less than a minute or longer than a day. We will remove these trips while cleaning the data to ensure accuracy using the 'dplyr' tool In R Studio desktop ✔️

>cleaned_data <- cleaned_data %>%
  >filter(duration >= 60 & duration < 60*60*24)



  



# Share Results

The analysis was conducted in R and includes data cleaning, exploration, and visualization. The following questions were addressed in the analysis:

How many are casuals compared to annual riders?

What are the most popular routes and destinations for Cyclistic's customers?

How do the usage patterns differ by time of day, day of the week, and month?

# Who Are the Stakeholders?
Lily Moreno
The director of marketing and your manager. Moreno is responsible for the development of campaigns
and initiatives to promote the bike-share program. These may include email, social media, and other channels.

# Share Results
![alt text](https://github.com/databubs/Cyclists_2023/blob/main/Days%20Of%20Riders.png)

![alt text](https://github.com/databubs/Cyclists_2023/blob/main/Percentage_Of_Rides_By_Member%20type.png)

![alt text](https://github.com/databubs/Cyclists_2023/blob/main/Cyclists_Members.png?raw=true)

# Codes via GGPLOT2 Explained





# Results
The analysis revealed several insights about Cyclistic's customers:

The majority of customers are members rather than casual riders.
Members tend to use the bikes more frequently and for shorter periods of time than casual riders.
Bike usage varies by time of day, with peak usage in the morning and evening rush hours.
Bike usage also varies by day of the week, with higher usage on weekdays than on weekends.
The most popular routes and destinations are located in the city center and near tourist attractions.
Conclusion
The results of the analysis provide valuable insights for Cyclistic's business strategy. For example, they can use the information about their main users to target marketing efforts more effectively, or adjust pricing and incentives to encourage more casual riders to become members. The insights about usage patterns can also inform decisions about bike placement and maintenance.

# Files
cyclistic_analysis.Rmd: R Markdown file containing the code and analysis.

cyclistic_analysis.html: HTML file containing the knitted R Markdown report.

data/2020_cyclistic_tripdata.csv: Raw data used for the analysis.

data/cyclistic_cleaned_data.csv: Cleaned data used for the analysis.
Dependencies


# Packages 
The analysis was conducted using R version 4.1.0 and the following R packages:

tidyverse
lubridate
ggplot2
dplyr



