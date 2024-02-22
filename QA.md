What are your risk areas? Identify and describe them.

Some Risk areas are the names of the column names

ALTER TABLE all_sessions
RENAME COLUMN total_ordered TO total_ordered;

Another risk area was the NULL data set and so the following query solved it 

QA Process:
Describe your QA process and include the SQL queries used to execute it.

DELETE FROM all_session
WHERE total_ordered IS NULL
   OR fullvisitorId IS NULL
   OR pageviews IS NULL
   OR sessionQualityDim IS NULL;

