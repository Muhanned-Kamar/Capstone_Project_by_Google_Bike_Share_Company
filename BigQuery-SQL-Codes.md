# BigQuery

Here i will be listing the queries used to get the data used in Tabluea.

## Step 1 (Checking Tables)

For each table uploaded we need to test them and make sure that the data is error free and have the right format.

### Query 1 (Testing Tables)

    SELECT *

    FROM  `voltaic-quest-344909.project_case_study_1.year_2021_data` -- dont forget to use your table destination 

    -- checking all the tables from June to December

## Step 2 (Manipulation and Cleaning)

Creating one table, so it is easier to run queries without going through 12 tables. And checking the credibilty of the data to ensure the data is not bias.

### Query 1 (Table Creationo or Combination)

    CREATE TABLE `voltaic-quest-344909.project_case_study_1.year_2021_data` -- dont forget to use your table destination 

    AS ( 
    -- Data for the table year_2021

    SELECT * FROM `voltaic-quest-344909.project_case_study_1.jan_data` -- Jan Data

    UNION ALL

    SELECT * FROM `voltaic-quest-344909.project_case_study_1.feb_data` -- Feb Data

    UNION ALL

    SELECT * FROM `voltaic-quest-344909.project_case_study_1.march_data` -- March Data

    UNION ALL

    SELECT * FROM `voltaic-quest-344909.project_case_study_1.april_data` -- April Data

    UNION ALL

    SELECT * FROM `voltaic-quest-344909.project_case_study_1.may_data` -- May Data

    UNION ALL

    SELECT * FROM `voltaic-quest-344909.project_case_study_1.june_data` -- June Data

    UNION ALL

    SELECT * FROM `voltaic-quest-344909.project_case_study_1.july_data` -- July Data

    UNION ALL

    SELECT * FROM `voltaic-quest-344909.project_case_study_1.aug_data` -- Aug Data

    UNION ALL

    SELECT * FROM `voltaic-quest-344909.project_case_study_1.sep_data` -- Sep Data

    UNION ALL

    SELECT * FROM `voltaic-quest-344909.project_case_study_1.oct_data` -- Oct Data

    UNION ALL 

    SELECT * FROM `voltaic-quest-344909.project_case_study_1.nov_data` -- Nov Data

    UNION ALL

    SELECT * FROM `voltaic-quest-344909.project_case_study_1.dec_data` -- Dec Data 

    ); 

    -- Created a table called 'year_2021_data' 
### Query 2 (Cleaning)

    DELETE

    FROM `voltaic-quest-344909.project_case_study_1.year_2021_data`

    WHERE ride_length= '00:00:00' or ride_id is NULL;

    -- Here we used DELETE clause to ensure that there is no ride ride_length = '00:00:00' or ride_id with a NULL value.

## Step 3 (Analysis)

The analysis done throught the project to get the tables needed to answer the business questions

### Query 1 (Average Users Per Day)

    SELECT member_casual, 

    COUNT(day_of_week)/ 360 AS users_per_day,

    case when day_of_week = 1 then 'Sunday' 

         when day_of_week = 2 then 'Monday' 
     
         when day_of_week = 3 then 'Tuesday' 
     
         when day_of_week= 4 then 'Wednesday' 
     
         when day_of_week = 5 then 'Thrusday' 
     
         when day_of_week = 6 then 'Friday' 
     
         when day_of_week = 7 then 'Saturday' end  AS day

    FROM `voltaic-quest-344909.project_case_study_1.year_2021_data`

    GROUP BY day_of_week , member_casual
    ORDER BY COUNT (day_of_week) DESC

    -- I used case clause to change the numbers listed in the table to its corresponding day (Sunday = 1 to Saturday = 7)
    
### Query 2 (Average User Ride Time Per Day)

    SELECT day_of_week, member_casual, 
    
    AVG( (EXTRACT(MINUTE FROM  started_at) ) + (EXTRACT (HOUR FROM started_at)*60)) AS total,

    case when day_of_week = 1 then 'Sunday' 
    
         when day_of_week = 2 then 'Monday' 
         
         when day_of_week = 3 then 'Tuesday' 
         
         when day_of_week= 4 then 'Wednesday'  
         
         when day_of_week = 5 then 'Thrusday' 
         
         when day_of_week = 6 then 'Friday' 
         
         when day_of_week = 7 then 'Saturday' end  AS day

    FROM `voltaic-quest-344909.project_case_study_1.year_2021_data`

    GROUP BY day_of_week , member_casual
    
    -- Avg User ride time in mins across the year per day
    
### Query 3 (Number Of Users Per Day)

This part is done in two different queries to get the outcome needed

  #### First Query (Table Creation to get Date only Not Date and Time)

    CREATE TABLE `voltaic-quest-344909.project_case_study_1.trial_1`

    AS (
    SELECT  ride_id AS ride_id_2 , CAST (started_at AS date) AS date_2, 
   
    member_casual AS member_casual_2 , start_lat AS start_lat_2 , start_lng AS start_lng_2

    FROM `voltaic-quest-344909.project_case_study_1.year_2021_data`
    )
  #### Second Query (Number Of Users Per Day)

    SELECT  date , member_casual , COUNT (member_casual) AS number_of_users

    FROM `voltaic-quest-344909.project_case_study_1.trial_1`

    GROUP BY  date , member_casual 

    ORDER BY  date DESC

    -- Created a table for the required data to of user across the year 

### Query 4 (Maximum User Ride Time)

    SELECT member_casual, 

    MAX( (EXTRACT(MINUTE FROM  started_at) ) + (EXTRACT (HOUR FROM started_at)*60)) AS total,
   
    FROM `voltaic-quest-344909.project_case_study_1.year_2021_data`

    GROUP BY member_casual

    -- Evaluating the maximum ride time of the member and casual users

### Query 5 (Users Usage Location)

This part is done in two different queries to get the outcome needed

  #### First Query

