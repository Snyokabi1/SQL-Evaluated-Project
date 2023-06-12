Answer the following questions and provide the SQL queries used to find the answer.

    
**Question 1: Which cities and countries have the highest level of transaction revenues on the site?**


SQL Queries:
--Question 1: Which cities and countries have the highest level of transaction revenues on the site?

SELECT SUM(revenue)DESC, country
FROM analytics
JOIN all_sessions
ON all_sessions.fullvisitorid = analytics.fullvisitorid 
WHERE revenue > 0
GROUP BY country




Answer: United States




**Question 2: What is the average number of products ordered from visitors in each city and country?**


SQL Queries: --Question 2: What is the average number of products ordered from visitors in each city and country?

SELECT AVG(units_sold)DESC, city, country
FROM analytics
JOIN all_sessions
ON all_sessions.fullvisitorid = analytics.fullvisitorid 
JOIN products
ON products.sku = all_sessions.productsku
WHERE units_sold>0
GROUP BY city, country



Answer:





**Question 3: Is there any pattern in the types (product categories) of products ordered from visitors in each city and country?**


SQL Queries:



Answer:





**Question 4: What is the top-selling product from each city/country? Can we find any pattern worthy of noting in the products sold?**


SQL Queries:



Answer:





**Question 5: Can we summarize the impact of revenue generated from each city/country?**

SQL Queries:



Answer:







