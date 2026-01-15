# pandas-Retail-Business-Data-Analysis-Project-
Project Overview
Analysis of online retail transaction data (2009-2011) containing 1,067,371 transactions worth £20.8M from a UK-based retail company.

Dataset Information
Source: UCI Online Retail II Dataset

Period: December 2009 - December 2011

Transactions: 1,067,371

Products: 5,469 unique items

Customers: 5,881 identified customers

Countries: 38 countries

Business Questions Analyzed
1. Revenue Analysis
Objective: Identify total revenue and top-performing products

Challenges & Solutions:

Negative quantities discovered (22,950 transactions, 2.15% of data)

Identified as returns/cancellations, filtered for sales analysis

Missing Customer IDs (243,007 rows, 22.7% of data) marked as "Unknown"

Created revenue column: Quantity × Price

Findings:

Total Sales Revenue: £20,814,292

Top Product: REGENCY CAKESTAND 3 TIER (£344,563, 1.66% of total)

Revenue Concentration: Top 10 products = 9.81% of revenue

Business Insight: Healthy diversification (not dependent on few products)

2. Customer Analysis
Objective: Identify top customers and purchase patterns

Challenges & Solutions:

Filtered out missing Customer IDs for valid analysis

Handled case sensitivity in column names ("Customer ID" vs "customer id")

Corrected grouping logic for customer aggregation

Findings:

Top Customer: #18102 (£608,822 spent)

Customer Concentration: Top 10 customers = 15% of revenue

Unique Customers: 5,881 with valid IDs

Business Insight: Moderate dependency on key accounts

3. Time Analysis
Objective: Identify seasonal and time-based patterns

Challenges & Solutions:

Date format issues: All months showed as December initially

Debugged datetime conversion: Original strings in '2009-12-01 07:45:00' format

Used pd.to_datetime() with errors='coerce' parameter

Extracted month, weekday, and hour components correctly

Findings:

Best Month: November (£2,979,769, holiday season peak)

Best Weekday: Thursday (£4,252,798, pre-weekend shopping)

Best Hour: 12:00 noon (£2,871,299, lunch hour peak)

Anomaly: Saturday sales extremely low (£9,803 vs £4.2M Thursday)

Business Insight: Clear weekly and seasonal patterns for staffing and inventory planning

4. Geographic Analysis
Objective: Analyze market distribution

Challenges & Solutions:

Correct calculation of UK vs International percentages

Fixed Series vs number calculation errors

Proper grouping and filtering by country

Findings:

UK Revenue: £17,712,680 (85.1% of total)

International Revenue: £3,101,617 (14.9% of total)

Top 5 International Markets: Ireland, Netherlands, Germany, France, Australia

Business Insight: Domestic-focused business with established EU presence

5. Product Performance Analysis
Objective: Analyze product categories and purchase frequency

Challenges & Solutions:

Initial categorization placed 61% of products in "Other" category

Improved keyword-based categorization reduced "Other" to 42.4%

Created 10 meaningful categories from product descriptions

Fixed incorrect grouping syntax multiple times

Findings:

Average Product Price: £3.91

Most Frequently Purchased: WHITE HANGING HEART T-LIGHT HOLDER (5,783 purchases)

Revenue by Category: Bags & Packaging (12.4%), Home Decor (11.3%), Kitchenware (9.1%)

Business Insight: Clear product category performance for inventory and marketing focus

Technical Challenges & Solutions
Data Loading Issues:
Kaggle file path errors: Corrected path syntax from backslash to forward slash

Memory management: Used nrows parameter for initial exploration

File format: Handled both CSV and Excel formats

Data Quality Issues:
Negative quantities: Identified as returns, filtered for sales analysis

Missing values: Strategic handling based on business context

Inconsistent formatting: Standardized text processing

Date parsing: Correct datetime conversion with error handling

Analysis Errors:
Grouping mistakes: Corrected grouping logic multiple times

Percentage calculation errors: Fixed denominator issues

Case sensitivity: Standardized column name references

Series vs scalar operations: Properly extracted values from pandas Series

Key Business Insights
Revenue & Product Strategy:
Business is well-diversified with top 10 products contributing only 9.81% of revenue

Long tail of products drives majority of sales

Average transaction value provides pricing strategy insights

Customer Insights:
Clear VIP customer identification for relationship management

Moderate customer concentration indicates healthy business mix

Opportunities for customer loyalty programs

Operational Planning:
Clear seasonal patterns for inventory planning (November peak)

Weekly patterns inform staffing schedules (Thursday peak)

Hourly patterns guide store operations and promotions

Market Strategy:
Strong domestic UK focus with growth opportunities in EU markets

Established presence in key European countries

Limited global reach presents expansion opportunities

Product Management:
Clear category performance for strategic focus

Need for improved product categorization systems

Pricing strategy insights from category analysis

Tools & Technologies Used
Python 3.11

Pandas for data manipulation

Kaggle platform for dataset access and computation


Lessons Learned
Real business data is messy and requires extensive cleaning

Business context is essential for correct data interpretation

Iterative improvement is necessary for analysis quality

Documentation of decisions and assumptions is critical

Error handling and debugging are ongoing processes in data analysis

Recommendations for the Business
Focus marketing efforts on November (peak month) and Thursday (peak day)

Develop VIP program for top 10 customers driving 15% of revenue

Expand EU market presence in already successful countries

Improve product categorization for better inventory management

Investigate Saturday sales anomaly for potential revenue opportunity

Consider pricing strategy adjustments based on category performance

Project Value
This analysis provides actionable insights for business strategy, operational planning, and growth opportunities based on comprehensive analysis of 2+ years of transaction data. The project demonstrates practical data analysis skills with real-world business applications.
