Answer the following questions and provide the SQL queries used to find the answer.

    
**Question 1: Which cities and countries have the highest level of transaction revenues on the site?**


SQL Queries:
SELECT city, country, SUM("totalTransactionRevenue") AS total
    FROM all_sessions
	WHERE "totalTransactionRevenue" IS NOT NULL
	GROUP BY city, country
    ORDER BY total DESC;


Answer: Atlanta USA, Sunnyvale USA, Televiv Israel, Los Angeles USA, Seatte USA


**Question 2: What is the average number of products ordered from visitors in each city and country?**


SQL Queries:
SELECT all_sessions.country, all_sessions.city, all_sessions."visitId", sales_by_sku.total_ordered
    FROM sales_by_sku
    JOIN all_sessions ON sales_by_sku."productSKU" = all_sessions."productSKU"
    ORDER BY sales_by_sku.total_ordered DESC;

Larry AI was a great assistance in realizing column titles with quotation marks surrounding it. Without it, PGadmin4 was not picking up the feed. 

Answer: United States (Country), City (N/A) Product ordered: 456/visitorId
        South Korea, Seoul, 456/VisitorId
        Malaysia, N/A 456
        Spain, N/A 456

**Question 3: Is there any pattern in the types (product categories) of products ordered from visitors in each city and country?**


SQL Queries:
SELECT all_sessions."visitId", all_sessions."v2ProductName", all_sessions.city, all_sessions.country, sales_by_sku.total_ordered
    FROM all_sessions
    JOIN sales_by_sku ON all_sessions."productSKU" = sales_by_sku."productSKU"
    ORDER BY city DESC; 
    ORDER BY "v2ProductName"; -- varying column name to analyze response of visitors per factor. 

Answer: Hi Quantity of ballpoint LED light pens purchased inn United States, Germany, South Korea, Japan, India. Visitors seem to be purchasing high quantity of products. While Google products seem not too appealing to vistors across various countries and cities. Based on Product, Youtube short sleeves are not popular irrespective of location. 



**Question 4: What is the top-selling product from each city/country? Can we find any pattern worthy of noting in the products sold?**


SQL Queries:
SELECT all_sessions."visitId", all_sessions."v2ProductName", all_sessions.city, all_sessions.country, sales_by_sku.total_ordered
FROM all_sessions
JOIN sales_by_sku ON all_sessions."productSKU" = sales_by_sku."productSKU"
ORDER BY "total_ordered" DESC;

Answer: Ballpoint LED Light Pen





**Question 5: Can we summarize the impact of revenue generated from each city/country?**

SQL Queries:



Answer:







