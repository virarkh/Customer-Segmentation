# Use Case Summary
## Objective Statement
- Get business insight about how growth the orders from 2011 to 2014 by year and month.
- Get business insight about when monthly peak orders happened from January 2011 to December 2014.
- Get business insight about when peak date orders happend from January 2011 to December 2014
- To create customer segmentation using RFM Quantile.
- Get business insight for each customers based on label defined such as Loyal Customer, Big Spenders, Lost Cheap Customers, Best Customers and Almost Lost.

## Challenges
- Large size of data, can not be maintained by excel or spreadsheet.
- Dataset have an incorrect data type.
- There is no information where the orders happend.

## Methodology
- Descriptive Analysis: to find out information on current conditions based on the data that has been collected.
- Graph Analysis: provide information from the graph.
- Segment Analysis : RFM Quantile.

## Business Benefit
- Know how to treat customers based on their behavior when customers order.
- Help the business team provide products or services based on the behavior of each customer.

## Expected Outcome
- Know how growth the order from 2011 to 2014 by year and month.
- Know when monthly peak from January 2011 to December 2014.
- Know when peak date from January 2011 to December 2014.
- Create customer segmentation using RFM Quartile.
- Know the label each customers based on label defined such as Loyal Customer, Big Spenders, Lost Cheap Customers, Best Customers and Almost Lost.

# Business Understanding
**Business Retail** is a business that involves selling goods or services to customers in units or retail. Consumers who buy products or services on a retail basis aim to consume them or use them personally and do not resell them. So from here we get business questions about customer segmentation as follows:
- How growth the order from 2011 to 2014 by year dan month ?
- When monthly peak orders happend from January 2011 to December 2014 ?
- When peak date orders happend from January 2011 to December 2014 ?
- How create customer segmentation using RFM Quartile ?
- How many customers based on label defined such as Loyal Customer, Big Spenders, Lost Cheap Customers, Best Customers and Almost Lost ?

# Data Understanding
## Source Data
The dataset has 4 columns and 5009 rows. This data from 4 January 2011 to 31 December 2014. <br>
From https://www.kaggle.com/datasets/siddinho/sample-orders-dataset-retail

## Data Dictionary
- order_date : the day when customers order
- order_id : unique number for each order
- customer : people who ordered
- grand_total : total items ordered by customers

# Data Preparation
- Programming Language : Python Version 3.9.12
- Library : pandas, numpy, matplotlib, seaborn, datetime, scipy, sklearn, plotly, feature_engine, warning 

# Data Cleaning
- In order_date column which stored order date customer, it should store data in date data type. But from the data we have it is known that this column stores data in objects data type. So we decided to change data type from object to date.
- From the order_date column, data also separated by year, month and date. Then saved into a new column with column names namely year, month and date.
