What issues will you address by cleaning the data?
standardize formats time, productprice




Queries:
Below, provide the SQL queries you used to clean your data.
-- all_sessions table time cplumn -update the number of digits to 6, left padding with zeros. to be followed by conversion to time format
ALTER TABLE all_sessions
ALTER COLUMN time
TYPE VARCHAR
USING LPAD(time::VARCHAR, 6, '0');


