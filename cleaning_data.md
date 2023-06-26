What issues will you address by cleaning the data?

standardize formats time, productprice


Queries:
Below, provide the SQL queries you used to clean your data.

# all_sessions.time column 
# update the number of digits to 6, left padding with zeros. to be followed by conversion to time format

'''

ALTER TABLE all_sessions

ALTER COLUMN time

TYPE VARCHAR

USING LPAD(time::VARCHAR, 6, '0');

'''

--conversion to 00:00:00 format SUBSRTRING
--Query to convert analytics.timeonsite to time format HH:MM:SS 



# all_sessions, totaltransactionrevenue/100000

ALTER TABLE all_sessions
ALTER COLUMN totaltransactionrevenue TYPE DECIMAL(18, 3)
USING totaltransactionrevenue::numeric(18, 3);

UPDATE all_sessions
SET totaltransactionrevenue = totaltransactionrevenue / 1000000.0




ALTER TABLE analytics

ALTER COLUMN timeonsite

TYPE VARCHAR

USING LPAD(timeonsite::VARCHAR, 6, '0');

UPDATE analytics

SET timeonsite = CONCAT(
   
    SUBSTRING(timeonsite, 1, 2),
  
    ':',
    
    SUBSTRING(timeonsite, 3, 2),
    
    ':',
   
    SUBSTRING(timeonsite, 5, 2)
    
);


--convert analytics.visitstarttime to TIMESTAMPTZ format/datatype
ALTER TABLE analytics

ALTER visitstarttime 

TYPE TIMESTAMPTZ

USING timezone('UTC', TO_TIMESTAMP(visitstarttime))

