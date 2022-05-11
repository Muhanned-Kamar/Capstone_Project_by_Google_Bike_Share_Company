# Project 1: Google Data Analytics Capstone Project 

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
1.Sorted by ‘started_at’
2.Filtered all columns to check for NULLS
3.Checked for any duplication in the ‘ride_id’
4.Made a new column ‘ride_length’ to calculate the length of each ride time
5.Made a new column to calculate the day of week 
6.Used conditional formatting for ride_length’ to check if ant errors where there

 -Swapped some of the stared_at & ended_at data because they were inputted wrong
BiqQuery (SQL):
1.To ensure credibility and integrity
	-Checked for null and tested each table
	-Checked for duplication in the ride_id 
2.Combined all tables into one large table then checked ride_lenght = ‘ 0:00:00’ to remove it which is considered the time of the maintenance of the bikes.
3.Checked formatting of each of the attributes.

After doing all of this steps the data was ready for the next phase (Analyze Phase)where we will begin to calculate and try to find trends and insights so we can answer the questions Moreno asked.
