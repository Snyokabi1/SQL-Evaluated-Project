What are your risk areas? Identify and describe them.

--Risk of affecting data integrity during the cleaning process

--Lack of contextual, industry or subject matter knowledge may lead to wrong conclusions during the data manipulation

QA Process:

Describe your QA process and include the SQL queries used to execute it.

Examining whole database, example. How many tables and how they are related, and what each represents, 

SELECT *
From analyticsS

Retrieving sample data by adding a LIMIT BY clause to the above query to further examime a smaller sample of rows

Checking for inconsistencies like shipdate should come after order date

Range of timelines, quantities, 


Examining the individual tables, checking for adherance to constraints
unique values like customerid, orderid, productid should not have duplicates, 

SELECT visitid
FROM analytics

should have consistent results to 

SELECT DISTINCT visitid
FROM analytics

Checking data relationships to other tables, identify primary and foreign keys

Using COUNT, DISTINCT, MIN, MAX, and AVG to profile data, characteristics and identify potential data quality issues. Checking for outliers, questioning null values
Ommitting data deemed irrelevant, or duplicate for example, columns without values
