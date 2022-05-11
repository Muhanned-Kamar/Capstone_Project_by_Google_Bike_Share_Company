# Project 1: Google Data Analytics Capstone Project 

## Introduction

This is a case study for a bike share company named ‘Cyclistic’ located in Chicago,  I will be testing my abilities as a junior data analyst working with the marketing analyst team to achieve the company’s future success which depends on maximizing the number of annual memberships. The main question to be answered through the analysis is how casual riders and annual members us Cyclistic bikes differently. From these insights, my team will design a new marketing strategy to convert casual riders into annual members. But first, Cyclistic executives must approve my recommendations, so I must back up with compelling data insights and professional data visualizations.

Characters and teams 

- **Cyclistic**: A bike-share program that features more than 5,800 bicycles and 600 docking stations. Cyclistic sets itself apart by also offering reclining bikes, hand tricycles, and cargo bikes, making bike-share more inclusive to people with disabilities and riders who can’t use a standard two-wheeled bike. The majority of riders opt for traditional bikes; about 8% of riders use the assistive options. Cyclistic users are more likely to ride for leisure, but about 30% use them to commute to work each day. 
- **Lily Moreno**: The director of marketing and your manager. Moreno is responsible for the development of campaigns and initiatives to promote the bike-share program. These may include email, social media, and other channels. 
- **Cyclistic marketing analytics team**: A team of data analysts who are responsible for collecting, analyzing, and reporting data that helps guide Cyclistic marketing strategy. You joined this team six months ago and have been busy learning about Cyclistic’s mission and business goals — as well as how you, as a junior data analyst, can help Cyclistic achieve them. 
- **Cyclistic executive team**: The notoriously detail-oriented executive team will decide whether to approve the recommended marketing program.

### About the company 

In 2016, Cyclistic launched a successful bike-share offering. Since then, the program has grown to a fleet of 5,824 bicycles that are geo tracked and locked into a network of 692 stations across Chicago. The bikes can be unlocked from one station and returned to any other station in the system anytime. 

Until now, Cyclistic’s marketing strategy relied on building general awareness and appealing to broad consumer segments. One approach that helped make these things possible was the flexibility of its pricing plans: single-ride passes, full-day passes, and annual memberships. Customers who purchase single-ride or full-day passes are referred to as casual riders. Customers who purchase annual memberships are Cyclistic members. 

Cyclistic’s finance analysts have concluded that annual members are much more profitable than casual riders. Although the pricing flexibility helps Cyclistic attract more customers, Moreno believes that maximizing the number of annual members will be key to future growth. Rather than creating a marketing campaign that targets all-new customers, Moreno believes there is a very good chance to convert casual riders into members. She notes that casual riders are already aware of the Cyclistic program and have chosen Cyclistic for their mobility needs. 

Moreno has set a clear goal: Design marketing strategies aimed at converting casual riders into annual members. In order to do that, however, the marketing analyst team needs to better understand how annual members and casual riders differ, why casual riders would buy a membership, and how digital media could affect their marketing tactics. Moreno and her team are interested in analyzing the Cyclistic historical bike trip data to identify trends.

In order to answer the key business questions, I will follow the steps of the data analysis process: ask, prepare, process, analyze, share, and act. From those steps I will be able to answer those questions with facts from the provided dataset of the past year 2021(Note: The datasets have a different name because Cyclistic is a fictional company. For the purposes of this case study, the datasets are appropriate and will enable you to answer the business questions. The data has been made available by Motivate International Inc. under this [license](https://ride.divvybikes.com/data-license-agreement).)

![image](https://user-images.githubusercontent.com/105308533/167831289-2f2f051d-21e9-44f4-a9ac-19435d8f9b87.png)


Used the data analysis process: ask, prepare, process, analyze, share, and act to answer the questions listed in the PDF file.

## ASK

In this phase I will be identifying the business task and considering key stakeholders. and I will be delivering you a clear statement of the business task.
The problem we are ,as a company, trying to solve is not consider a problem but a rather an enhancement to the company in which we are trying to increase the company’s net profit. Our director of marketing Moreno believes that by converting the casual riders to member riders will increase the company’s future success. So, the main point is to convince casual riders to purchase the annual membership. From here we will try to answer 3 questions Moreno assigned to us and they are :

1. How do annual members and casual riders use Cyclistic bikes differently?
2. Why would casual riders buy Cyclistic annual memberships?
3. How can Cyclistic use digital media to influence casual riders to become members?

To answer those question first we need to see the dataset we will be dealing with and try to organize, ensure credibility, who can access the data, verify the data integrity, see if this data can help me answer the question listed by Moreno, mention any problems with the data, how would it be stored, and a description of all the data sources used, all this will be answered in the next phase the **Prepare Phase**.

## Prepare

This phase will be our first interaction where we will be going through it and try and organize everything so it would be easy to access, clean, and ensure that it is not bias.

First, we need to download the data through this link [Cyclistic-trip data ' Download files beginning with 202101 to 202112'](https://divvy-tripdata.s3.amazonaws.com/index.html)
After download the data I will be storing it in a local folder first called ‘original_data’ which will hold all the original downloaded data then I copied all the data into a new folder ‘clean_data’. From this step I located the data on my local computer so I can start the cleaning process.

The data will be organized by month starting from June to December. So, if anyone from the market analytical team or Moreno would like to access those files it would be easy to understand. Then I begin go through the data to see if there is any bias data, after a quite time inspecting the data, I found that there could be bias if I did not check for the ride time of each trip, ride id, start location, end location, and the user listed. Checking the data, I found that the format is all the same across all the 12 csv files which indicated that the data is credible and not bias.

The Cyclistic data was taken from Lyft Bikes and Scooters bikeshare company, and the data was license above. And the accessibility to the on running file is given to the marketing team and Moreno but without accesses to modification to any of the files unless an email is sent with the modification needed to be done then I will consider either modifying it myself or giving access to whom sent the email to do the modification while keeping an eye on the modification.

Going through the data life cycle I found that it is unified across all 12 months which indicates that the data has integrity.

Going to next phase **Process Phase**, there where the cleaning process takes place with all it details.

## Process

In this phase the data will be cleaned and manipulated to ensure its cleanness, integrity, and the working effectiveness of the data.
First , the tools used that will be used will be answer for why this tool will be used starting with :

Excel:

This tool is a good start so I can identify the attributes, formats, and check for errors. Excel works best with small data so we consider that each month is a small data from there we can check each month to ensure credibility and integrity throughout the whole data year.

BiqQuery:

BigQuery works faster than excel when handling large data, so I used it as a way to ensure that the data is cleaned and has integrity from there, we will be ready to analyze data.

Second,  this is the part for documenting the cleaning process and manipulation of the data. This process took place in both Excel and BigQuery.
Excel cleaning and manipulation process:
1. Sorted by ‘started_at’
2. Filtered all columns to check for NULLS
3. Checked for any duplication in the ‘ride_id’
4. Made a new column ‘ride_length’ to calculate the length of each ride time
5. Made a new column to calculate the day of week 
6. Used conditional formatting for ride_length’ to check if ant errors where there
	- Swapped some of the stared_at & ended_at data because they were inputted wrong
BiqQuery (SQL):
1. To ensure credibility and integrity
	- Checked for null and tested each table
	- Checked for duplication in the ride_id 
2. Combined all tables into one large table then checked ride_lenght = ‘ 0:00:00’ to remove it which is considered the time of the maintenance of the bikes.
3. Checked formatting of each of the attributes.

After doing all of this steps the data was ready for the next phase **Analyze Phase** where we will begin to calculate and try to find trends and insights so we can answer the questions Moreno asked.

## Analyze Phase

In this part the real exploration will begin, using SQL (BigQuery) as the analysis tool, we begin by ensuring that the table is organized ,has no duplicated and sorted by ‘started_at’. Checked the format again then manipulated the data to get insights and trends. Found some useful information such as casual users are more than member, but they have the same maximum ride time across the year. Found a relationship between months, days, ride time, and users. All the tables and queries are saved on BigQuery. To summarize the analysis, I will be listing the process made:
1. Made a table combing all the months table
2. Calculated the average users per day (users_per_day)
3. Created a new table with date fir number of users per day (number_of_users_per_day)
4. Created  the average user ride time per day (avg_user_ride_time)(avg_query)
5. Created maximum ride time user table (max_member_casual_ride)
6. Made a new table with date, lat, lng, id, and member or casual (adding_id_by_row_number) (location_new)

Finishing all of these table it is time to visualize all the tables made to furthermore identify and relate relationships in the tables, going to the next phase **Share Phase**.

## Share Phase

After a long time, cleaning, analyzing , and making sure the data is credible we finally came to the part where I can show Moreno and the marketing analytical team the findings and insights I gained from the data.

The data was clear of how the users used the bikes, the data showed us that the date of the usage matters, where it showed that the casual riders where more than the members and the highest number of users for both of casual and member riders was in the summertime from July decreasing to December even more during the weekends. This describes that the vacation time brings more users to use Cyclistic and all of that is show in my dashboard which you can access through this [link](https://public.tableau.com/app/profile/muhanned1728/viz/Trail_1_16515133908630/Dashboard2) . 

Now for the part with the recommendation so that the key findings are clear to every team member this part is called **Act Phase**.

## Act Phase

Going through all the phase we finally got to the last phase where we got a good view of the dashboards and what they give to us. Here will be giving recommendation after knowing that the casual users use Cyclistic bikes more in the summer and even more during the summer weekends.

### Recommendations 

1. I recommend that the company needs a new member ship packages so it can serve the summertime which has the highest casual rider’s users.
2. Marketing team should consider advertising before one month and during the summer months to get the most successful outcome from the marketing campaign.
3. We need to know if there are group or family riders, so we can make more membership packages to serve our clients and to be more unique in the market. 
4. Marketing campaigns could be near the beach where there are alot of users and location, for the socail media we can advertise on platforms like instagram, tiktok, and facebook we should include videos, packages and see if we can add bloggers, influencers, and vloggers to our campaign.
