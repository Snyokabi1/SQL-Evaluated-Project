Question 1:  Which cities and countries have the highest level of transaction revenues on the site?


SQL Queries:
'''

SELECT city, country, revenue, AVG(units_sold) units_sold

FROM analytics

JOIN all_sessions

ON all_sessions.fullvisitorid = analytics.fullvisitorid

JOIN products

ON products.sku = all_sessions.productsku

WHERE units_sold>0 AND revenue>1

GROUP BY analytics.revenue, city, country

ORDER BY revenue DESC, units_sold DESC

'''

Answer: United States: unknown city, Mountain view

Question 2: What is the average number of products ordered from visitors in each city and country?

SQL Queries: --Question 2: What is the average number of products ordered from visitors in each city and country?

'''

SELECT city, country, revenue, AVG(units_sold) units_sold

FROM analytics

JOIN all_sessions

ON all_sessions.fullvisitorid = analytics.fullvisitorid

JOIN products

ON products.sku = all_sessions.productsku

WHERE units_sold>0 AND revenue>1

GROUP BY analytics.revenue, city, country

ORDER BY units_sold DESC, revenue DESC

'''

Answer: the query returns units sold by city, with Mountain View USA leading with an average of 825

Question 3: Is there any pattern in the types (product categories) of products ordered from visitors in each city and country?

SQL Queries:

'''

SELECT sales_report.total_ordered, sales_report.name, city, country, visitid

FROM sales_report

JOIN all_sessions

ON sales_report.productsku=all_sessions.productsku

GROUP BY sales_report.total_ordered, sales_report.name, all_sessions.visitid,all_sessions.city, all_sessions.country

ORDER BY total_ordered DESC, city DESC, country DESC

'''

Answer: Yes, The most popular item in the first 3 most engaged cities is the Ballpoint LED Pen Seoul, South Korea is the most engaged non American city, falling 2nd overall,surpassing other American cities The ecommerce website is recieving attention from countires around the world, strategies to target customers in these cities and drive engagement up could be considered, based on the items of interest

Question 4: What is the top-selling product from each city/country? Can we find any pattern worthy of noting in the products sold?

SQL Queries: 

''' SELECT sales_report.total_ordered, sales_report.name, city, country, visitid

FROM sales_report

JOIN all_sessions

ON sales_report.productsku=all_sessions.productsku

GROUP BY sales_report.total_ordered, sales_report.name, all_sessions.visitid,all_sessions.city, all_sessions.country

ORDER BY total_ordered DESC, city DESC, country DESC 

'''

Answer: The Ballpoint LED Pen

Question 5: Can we summarize the impact of revenue generated from each city/country?

SQL Queries: ''' SELECT DISTINCT city, country, revenue, AVG(units_sold) units_sold

FROM analytics

JOIN all_sessions

ON all_sessions.fullvisitorid = analytics.fullvisitorid

JOIN products

ON products.sku = all_sessions.productsku

WHERE units_sold>0 AND revenue>1

GROUP BY analytics.revenue, city, country

ORDER BY revenue DESC, units_sold DESC '''

Answer: An unknown city (data missing) leads in revenue totalling 1587.06USD, followed by the city of Mountain view both in the USA, where majority of the buyers originate
