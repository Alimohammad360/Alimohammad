Answer the following questions and provide the SQL queries used to find the answer.

To whom it may concern, I cannot present the code properly below if it is not in the code format of github
    
**Question 1: Which cities and countries have the highest level of transaction revenues on the site?**


SQL Queries:
/*
SELECT city, country, SUM("totalTransactionRevenue") AS total
    FROM all_sessions
    WHERE "totalTransactionRevenue" IS NOT NULL
    GROUP BY city, country
    ORDER BY total DESC;
/**/

-- Answer: USA: San Francisco, Sunnyvale. Israel Tel Avev

**Question 2: What is the average number of products ordered from visitors in each city and country?**


--SQL Queries:
/*
SELECT 
    all_sessions.country, 
    all_sessions.city,  
    AVG(sales_by_sku.total_ordered) AS avg_products_ordered
FROM 
    sales_by_sku
JOIN 
    all_sessions ON sales_by_sku."productSKU" = all_sessions."productSKU"
GROUP BY 
    all_sessions.country, 
    all_sessions.city 
ORDER BY 
    avg_products_ordered DESC;
/**/


Larry AI was a great assistance in realizing column titles with quotation marks surrounding it. Without it, PGadmin4 was not picking up the feed. 

Answer: United States (Country), Rexburg, (City) Product ordered: 250.5/ VistorId
        South Korea, Seoul, 456/VisitorId
        Malaysia, N/A 456
        Spain, N/A 456

**Question 3: Is there any pattern in the types (product categories) of products ordered from visitors in each city and country?**


SQL Queries:
SELECT all_sessions."v2ProductCategory", all_sessions.city, all_sessions.country, SUM(sales_by_sku."total_ordered") AS total
    FROM all_sessions
	JOIN sales_by_sku ON all_sessions."productSKU" = sales_by_sku."productSKU"
	WHERE total_ordered >= 1
	GROUP BY 1,2,3
	ORDER BY total DESC


Answer: Hi Quantity of ballpoint LED light pens purchased inn United States, Germany, South Korea, Japan, India. Visitors seem to be purchasing high quantity of products. While Google products seem not too appealing to vistors across various countries and cities. Based on Product, Youtube short sleeves are not popular irrespective of location. 



**Question 4: What is the top-selling product from each city/country? Can we find any pattern worthy of noting in the products sold?**


SQL Queries:
SELECT all_sessions."v2ProductName", all_sessions.city, all_sessions.country, SUM(sales_by_sku."total_ordered") AS total
	FROM all_sessions
	JOIN sales_by_sku ON all_sessions."productSKU" = sales_by_sku."productSKU"
	WHERE city != 'not available in demo dataset'
	GROUP BY city, country, "v2ProductName"
	ORDER BY total DESC;

Answer: Per city and Country, the Nest indoor Camera was in summation the top selling product. Satiationary items were also very popular such as pens and journals. The pattern that was established seem to demonstrate personal items that ehanced lifestyles. 




**Question 5: Can we summarize the impact of revenue generated from each city/country?**

SQL Queries:
SELECT all_sessions.city, all_sessions.country FROM analytics 
	JOIN all_sessions ON analytics."visitId" = all_sessions."visitId"
	WHERE analytics.revenue is not NULL
	GROUP BY city, country


Answer: We can absolutely summarize the impact of Reveniue generated from each city and country. The results of the query demonstrated that Chicago had the greatest revenue impact while Mountain View was second. United States does take the first place in revenue impact across the board while Israel was second.







