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

### Query 2 (Table Creationo or Combination)

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

## Step 3

The analysis done was the average user ride time per day

