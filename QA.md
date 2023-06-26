What are your risk areas? Identify and describe them.

Risk of affecting data integrity during the cleaning process
Lack of contextual, industry or subject matter knowledge may lead to wrong conclusions during the data manipulation

QA Process:

Describe your QA process and include the SQL queries used to execute it.
Examining whole database, how many tables, and what each represents, checking for inconsistencies like shipdate should come after order date
Range of timeline, 

SELECT *
FROM (tablename)

Examining the individual tables, checking for unique values referenced in other tables. using JOINS 
Using COUNT, DISTINCT, MIN, MAX, and AVG to profile data, characteristics and identify potential data quality issues. Checking for outliers, questioning null values
Removing data deemed irrelevant, or duplicate using the Distinct and GROUP BY clauses
