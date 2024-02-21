Answer the following questions and provide the SQL queries used to find the answer.

    
**Question 1: Which cities and countries have the highest level of transaction revenues on the site?**


SQL Queries:
SELECT city, country, "totalTransactionRevenue"
    FROM all_sessions
    ORDER BY "totalTransactionRevenue";


Answer: Atlanta USA, Sunnyvale USA, Televiv Israel, Los Angeles USA, Seatte USA


**Question 2: What is the average number of products ordered from visitors in each city and country?**


SQL Queries:
SELECT all_sessions.country, all_sessions.city, all_sessions."visitId", sales_by_sku.total_ordered
FROM sales_by_sku
JOIN all_sessions ON sales_by_sku."productSKU" = all_sessions."productSKU"
ORDER BY sales_by_sku.total_ordered DESC;

Larry AI was a great assistance in realizing column titles with quotation marks surrounding it. Without it, PGadmin4 was not picking up the feed. 
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







