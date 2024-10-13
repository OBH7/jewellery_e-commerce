# Jewellery Pricing Analysis Report

## Overview
In this report, we dive into an analysis of jewellery pricing trends based on transaction data. The primary focus is to understand how different jewellery types, materials, and gemstones affect average prices, and how these prices have changed over time.

You can view the interactive visuals for this project on Tableau through the following link:  
[Jewellery Pricing Visualizations](https://public.tableau.com/views/Jewellery_visuals_2/Dashboard1?:language=en-US&publish=yes&:sid=&:redirect=auth&:display_count=n&:origin=viz_share_link)

## Dataset Insights
The dataset includes detailed records of jewellery sales, capturing information such as:
- Jewellery type (bracelets, earrings, etc.)
- Materials used (gold, silver, etc.)
- Gemstones (diamond, sapphire, etc.)
- Average price per item
- Number of transactions
- Total items sold
- Time-stamped data to track sales over time

This data offers a comprehensive view of the jewellery market, enabling us to study pricing trends and other significant patterns.

## Methodology
For the analysis, we used a combination of SQL and Python:
- **SQL** for data aggregation
- **Python** for initial data handling and preprocessing

Key SQL queries used in the analysis:

### 1. Jewellery Type Statistics
This query retrieves the average price, transaction count, and total items sold for each jewellery type:
```sql
SELECT Jewelry_Type, AVG(Price) AS Avg_Price, COUNT(*) AS Transactions, SUM(Quantity) AS Total_Items_Sold
FROM jewelry_data
GROUP BY Jewelry_Type
ORDER BY Avg_Price DESC;
2. Material and Gemstone Statistics
This query shows how different materials and gemstones influence average pricing:

sql
Copy code
SELECT Material, Gemstone, AVG(Price) AS Avg_Price, COUNT(*) AS Transactions
FROM jewelry_data
GROUP BY Material, Gemstone
ORDER BY Avg_Price DESC;
3. Price Trends Over Time
To examine price fluctuations over time, this query computes the average price by date:

sql
Copy code
SELECT DATE(Timestamp) AS Date, AVG(Price) AS Avg_Price
FROM jewelry_data
GROUP BY Date
ORDER BY Date;
Visualizations
We used Tableau to create a series of interactive visualizations for easier interpretation of the data. These include:

1. Jewellery Type Bar Chart
A bar chart that shows average prices across different types of jewellery. It helps identify which types are priced higher on average.

2. Heat Map for Materials and Gemstones
This heat map highlights average prices for different materials and gemstones. Darker shades indicate higher prices, helping to identify premium materials and combinations.

3. Line Chart for Price Trends
A line chart that plots average prices over time, allowing us to observe price fluctuations and trends.

Findings
Jewellery Type Statistics
Bracelets have the highest average price at $493.14 but fewer transactions compared to other types.
Earrings lead in terms of transaction volume with over 29,000 transactions, suggesting strong market demand despite a lower average price.
Material and Gemstone Analysis
Gold with diamonds is a premium category, with an average price of $504.11 and over 28,000 transactions.
Non-gemstone gold jewellery averages much lower, at $236.53, highlighting the price impact of gemstones.
Price Trends Over Time
The time-series analysis reveals fluctuations in jewellery pricing, possibly tied to seasonal trends or promotional periods.

Conclusion
The analysis provides valuable insights into pricing trends within the jewellery market. Earrings are in high demand, while gold with diamonds represents the most premium segment. These findings can help jewellery businesses optimize inventory and marketing strategies by focusing on high-demand, high-value segments.

Data Source
The dataset was sourced from an eCommerce purchase history, capturing two years of sales from December 2018 to December 2021. It was made available through the Open CDP project and includes over 130,000 records.

Dataset Title: eCommerce Purchase History from Jewellery Store
Size: 3 MB
License
This project is licensed under the MIT License. Please refer to the LICENSE.md file for details.