Jewellery Pricing Analysis Report
Overview
In this report, we dive into an analysis of jewellery pricing trends based on transaction data. Our goal is to understand how different jewellery types, materials, and gemstones affect average prices, and how these prices have changed over time.
Dataset Insights
The dataset contains detailed records of jewellery sales, including information about the type of jewellery, materials used, gemstones, average prices, number of transactions, and total items sold. The timestamps for each sale allow us to track price changes over time.
Methodology
To extract meaningful insights, we used SQL for data aggregation and Python for initial data handling. Here are the key SQL queries we executed:
1.	Jewellery Type Statistics This query gives us the average price, transaction count, and total items sold for each jewellery type:
sql
Copy code
SELECT Jewelry_Type, AVG(Price) AS Avg_Price, COUNT(*) AS Transactions, SUM(Quantity) AS Total_Items_Sold
FROM jewelry_data
GROUP BY Jewelry_Type
ORDER BY Avg_Price DESC;
2.	Material and Gemstone Statistics We examined how different materials and gemstones stack up in terms of average pricing:
sql
Copy code
SELECT Material, Gemstone, AVG(Price) AS Avg_Price, COUNT(*) AS Transactions
FROM jewelry_data
GROUP BY Material, Gemstone
ORDER BY Avg_Price DESC;
3.	Price Trends Over Time To understand how prices fluctuate, we tracked the average price by date:
sql
Copy code
SELECT DATE(Timestamp) AS Date, AVG(Price) AS Avg_Price
FROM jewelry_data
GROUP BY Date
ORDER BY Date;
Visualizations
Using Tableau, we created several visualizations to make the data more digestible:
1. Jewellery Type Bar Chart
We built a bar chart showing average prices across various jewelry types. Each bar represents a different type of jewellery, with its height indicating the average price.
2. Heat Map for Materials and Gemstones
A heat map illustrates the average prices for different materials and gemstones, with darker shades indicating higher prices. This visualization helps us quickly spot which materials are most valuable.
3. Line Chart for Price Trends
We plotted a line chart to visualize average prices over time. The x-axis represents dates, while the y-axis shows average prices. This allows us to see how prices have risen or fallen, highlighting any significant trends.
Findings
Jewellery Type Statistics
Here's a summary of the average prices and transaction counts for different jewelry types:
Jewellery Type	Avg Price	Transactions	Total Items Sold
jewelry.bracelet	493.14	6129	6129
electronics.clocks	426.78	165	165
jewelry.earring	396.29	29047	29047
From this, we see that earrings are the most frequently sold item, suggesting a strong market demand. While bracelets command higher prices, they have lower transaction volumes.
Material and Gemstone Analysis
The following highlights the average prices associated with various materials and gemstones:
Material	Gemstone	Avg Price	Transactions
gold	diamond	504.11	28835
gold	None	236.53	17243
Gold jewellery featuring diamonds clearly stands out as a premium offering, emphasizing the value of gemstones in pricing.
Price Trends Over Time
The line chart we created showcases fluctuations in average prices over time, revealing patterns that may indicate seasonal demand shifts.
Conclusion
This analysis uncovers valuable insights into jewellery pricing trends. It’s clear that certain jewellery types, like earrings, lead in sales volume, while gold with diamonds represents a high-value segment. Understanding these dynamics can help inform marketing strategies and inventory management. Looking ahead, we might consider exploring consumer behaviour and external factors influencing these pricing trends.

Data Source
The primary dataset utilized for this analysis is derived from eCommerce purchase history from a jewellery store, updated by Michael Kechinov three years ago. The dataset includes detailed records of 130,000 purchased jewellery products over a two-year period, specifically from December 2018 to December 2021. Each row in the dataset represents a purchased product, with multiple products from the same order identified by the order_id field.
This data was collected through the Open CDP project, an open-source customer data platform. The dataset can be accessed and downloaded as needed.
•	Dataset Title: eCommerce Purchase History from jewellery Store
•	Size: 3 MB



