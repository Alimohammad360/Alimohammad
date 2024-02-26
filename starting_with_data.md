Question 1: Does date impact total products ordered?

SQL Queries:
/*
SELECT "date", SUM("productQuantity") AS Quantity
FROM all_sessions 
GROUP BY "date"
HAVING SUM("productQuantity") IS NOT NULL 
ORDER BY "date" DESC;
/**

Answer: you can see that there is no pattern that really emerges when specified by day-to-day operations.



Question 2: How many users visited the site yearly

SQL Queries:
/*
SELECT EXTRACT(YEAR FROM "date") AS year,
COUNT("visitId") AS visit_count
FROM all_sessions
GROUP BY EXTRACT(YEAR FROM "date")
ORDER BY year;
/**

Answer:
2016 - 7004
2017 - 8130

To cite my sources, I asked assistance to Larry AI bot to help revise how to filter specific YEAR by date options as this was very advanced and I needed help

Question 3: How many year-to-year increase in sessions are there?

SQL Queries:

/*
SELECT Count("visitId"), YEAR("date") AS date FROM all_sessions
	GROUP BY date
/**
Answer:



Question 4: 

SQL Queries:

Answer:



Question 5: 

SQL Queries:

Answer:
