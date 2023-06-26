Question 1:  What percentage of total interactions resulted in a purchase

To get total visits to the site 
'''
SELECT COUNT(visitid)
FROM all_sessions

'''

Output 15,134
'''

SELECT COUNT(all_sessions.visitid)
FROM all_sessions
LEFT JOIN analytics
ON all_sessions.visitid = analytics.visitid
WHERE units_sold > 0

'''
output 151


#Answer: 0.001% of website interactions resulted in a purchase\


Question 2: What was the average time spent on site? How does this data present in terms of skewedness? 

SQL Queries: 

Still trying to come up with a working query for this data using the analytics.timeonsite column




'''

Answer: 

Question 3:
