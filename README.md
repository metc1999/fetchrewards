# Fetch Rewards Data Analysis - ReadMe

**Introduction**

This project involves analyzing datasets provided by Fetch Rewards, which include details about products, transactions, and users. The goal is to uncover actionable insights through data exploration and SQL queries, focusing on key metrics like popular brands, generational sales trends, and identifying power users.
________________________________________________________________________________________________________________________________________________________________________________________
Datasets Overview

Products Dataset: Contains information about product categories, manufacturers, brands, and barcodes.

Transactions Dataset: Includes details about receipts, purchase dates, scanned dates, store names, user IDs, barcodes, quantities, and sales values.

Users Dataset: Contains user IDs, account creation dates, birth dates, state, language, and gender.
________________________________________________________________________________________________________________________________________________________________________________________

**Queries and Results**

**Query 1: Top 5 Brands by Receipts Scanned (Users 21 and Over)**

Process:

Objective: Identify the top five brands based on the number of receipts scanned by users aged 21 and older.

Joined the transactions, users, and products datasets using user IDs and barcodes.

Filtered the data to include only users with valid birth dates and products with non-null, valid brand names.

Calculated user ages based on their birth dates and included only those aged 21 or older.

Grouped the data by brand, counted the associated receipts, and ranked the results to retrieve the top five brands.

Assumptions:

Users with missing birth dates or invalid brands are excluded.

"21 and over" is calculated using the user’s birth date and the current date.

Findings:

The top five brands by receipts scanned were:

Coca-Cola (314 receipts)

Annie’s Homegrown Grocery (288 receipts)

Dove (279 receipts)

Barefoot (276 receipts)

Oribe (252 receipts)
________________________________________________________________________________________________________________________________________________________________________________________

**Query 2: Percentage of Sales in Health & Wellness Category by Generation**

Process:

Objective: Determine the percentage of total sales in the Health & Wellness category contributed by each generation.

Assigned users to generational groups based on their ages:

Silent Generation (77+ years)

Boomers (58–76 years)

Gen X (42–57 years)

Millennials (26–41 years)

Gen Z (10–25 years)

Other (users outside these ranges)

Filtered the data to include only transactions with products in the Health & Wellness category.

Aggregated sales by generation and calculated the percentage of total category sales for each group.

Assumptions:

Users with missing birth dates were excluded as age is required for generation assignment.

Sales amounts (final_sale) were stored as strings and converted to numeric values for aggregation.

Findings:

Gen X contributed the most to Health & Wellness sales (36%), followed by Millennials at 34% and Boomers at 29%.

Younger generations (Gen X and Millennials) are key drivers of sales in this category.
_______________________________________________________________________________________________________________________________________________________________________________________

**Query 3: Fetch’s Power Users***

Process:

Objective: Identify "power users" of Fetch Rewards based on receipt activity.

Grouped transactions by user ID and counted the number of receipts per user.

Calculated the 99th percentile of receipt counts to define a threshold for power users.

Filtered the data to include users with receipt counts equal to or exceeding this threshold and ranked them in descending order of receipt counts.

Assumptions:

The 99th percentile is used to define power users, but this threshold can be adjusted.

Users with missing or invalid IDs are excluded.

Findings:

Power users were identified as those with three or more receipts scanned, representing the top 1% of users.

Six power users were identified, each scanning three receipts, indicating their high engagement with the platform.
________________________________________________________________________________________________________________________________________________________________________________________

**Conclusion**

This analysis highlights key insights about Fetch Rewards users and their behavior:

Coca-Cola, Annie’s Homegrown Grocery, Dove, Barefoot, and Oribe are the most popular brands among users aged 21+.

Health & Wellness sales are driven primarily by Gen X and Millennials, signaling a need to focus marketing efforts on these demographics.

The identified power users represent the most engaged portion of the user base, potentially serving as advocates for Fetch Rewards.
________________________________________________________________________________________________________________________________________________________________________________________

**Next Steps**

Investigate the missing and invalid data in the datasets to improve data quality.

Explore additional product categories and demographic trends to identify further growth opportunities.

Develop strategies to increase engagement among less active users based on insights from power users.

Contact

If you have any questions or need further clarifications, please don’t hesitate to reach out!

