Question 1: Does date impact total products ordered?

SQL Queries:

Answer: 



Question 2: How many users visited the site yearly

SQL Queries:

Answer:



Question 3: How many year-to-year increase in sessions are there?

SQL Queries:

SELECT Count("visitId"), YEAR("date") AS date FROM all_sessions
	GROUP BY date

Answer:



Question 4: 

SQL Queries:

Answer:



Question 5: 

SQL Queries:

Answer:
