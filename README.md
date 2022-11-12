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

# Exploratory Data Analysis
- **How growth the order from 2011 to 2014 by year and month ?**
![download](https://user-images.githubusercontent.com/113870155/201453821-a53a3beb-8d6c-4c30-8aea-0301d5410e73.png)

In **2011**, total orders around **484K**, which the **highest orders** occurred in September 2011 with growth up to 193.03% meanwhile the **lowest orders** occurred in February 2011 with a decrease up to 65%. <br>
In **2012** total orders around **470.5K**, in this year (2012) there was a 2.8% **decrease** in orders. Which the **highest orders** occurred in March 2012 with growth up to **215.04%** meanwhile the **lowest orders** occurred in January 2012 with a decrease up to **73.87%**. <br>
In **2013** total orders around **608.5K**, in this year (2013) there was a 29.31% **increase** in orders. Which the **highest orders** occurred in March 2013 with growth up to **215.04%** meanwhile the **lowest orders** occurred in January 2013 with a decrease up to **75.25%**. <br>
In **2014** total orders around **734K**, in this year (2014) there was a 20.63% **increase** in orders. Which the **highest orders** occurred in March 2014 with growth in orders of **165.77%** meanwhile the **lowest orders** occurred in January 2014 with a decrease up to **54.02%**. <br>
Based on the graph above, it can be concluded that the **highest** total orders from 2011 to 2014 occurred in **November and December**, while the **lowest** total orders from 2011 to 2014 occurred in **January and February**.

- **When monthly peak orders happend from January 2011 to December 2014 ?**
![download](https://user-images.githubusercontent.com/113870155/201453933-f5f84287-b8b5-46ab-82e8-a9158c9b70dc.png)

It is known that in a certain month has high total orders and low total order. Like in November which has peak monthly orders. Then in December and September also have a highest total order than other months. And the lowest total sales were in February and January. Meanwhile in April to August the total order is quite stable at around 150K.

- **When peak date orders happend from January 2011 to December 2014 ?**
![download](https://user-images.githubusercontent.com/113870155/201453984-7bbda83b-d116-48d4-a8a0-782311ad0f68.png)

On three days at the beginning of the month, 1st and 3rd date there was an increase in orders. Also in the middle of the month, which is on the 15th to 18th, there is also an increase in orders. Meanwhile on W4 which is the 24th to the 30th there is a decrease in orders.

# RFM Analysis
- **How create customer segmentation using RFM Quartile ?** <br>
RFM analysis is a marketing technique used to quantitatively rank and group customers based on the recency, frequency and monetary total of their recent transactions to identify the best customers and perform targeted marketing campaigns. RFM analysis ranks each customer on the following factors :
  - Recency. How recent was the customer's last purchase? Customers who recently made a purchase will still have the product on their mind and are more likely to purchase or use the product again. Businesses often measure recency in days. But, depending on the product, they may measure it in years, weeks or even hours.
  - Frequency. How often did this customer make a purchase in a given period? Customers who purchased once are often are more likely to purchase again. Additionally, first time customers may be good targets for follow-up advertising to convert them into more frequent customers.
  - Monetary. How much money did the customer spend in a given period? Customers who spend a lot of money are more likely to spend money in the future and have a high value to a business.

# Modeling Data : RFM Quantiles
- We split the metrics into segments using quantiles.
- We will assign a score from 1 to 4 to each Recency, Frequency and Monetary respectively.
- 1 is the highest value, and 4 is the lowest value.
- A final RFM score (Overall Value) is calculated simply by combining individual RFM score numbers.

![download](https://user-images.githubusercontent.com/113870155/201454648-3b43c9d5-2890-4d89-bb16-7517cf48094e.png)

- **How many customers based on label defined such as Loyal Customer, Big Spenders, Lost Cheap Customers, Best Customers and Almost Lost ?** <br>
Based on the results of Customer segmentation using RFM Quartile, customers are divided into 6 segments. Namely, Loyal Customers, Big Spenders, Lost Cheap Customers, Lost Customers, Best Customers and Almost Lost. <br>
33.59% from 384 customers or 129 customers are grouped into **Loyal Customers**. In this segment, customers have the highest order frequency than other segments. <br>
33.59% from 384 customers or 125 customers are grouped into **Big Spenders**. In this segment, the customer has the highest total order than to other segments. <br>
17.45% from 384 customers or 67 customers are grouped into **Lost Cheap Customers**. In this segment, customers are identified that churn because they haven't ordered for a long time, the frequency and total orders is also lower than other segments. <br>
8.07% from 384 customers or 31 customers are grouped into **Lost Customers**. In this segment, the customers behavior are almost the same with the lost customers segment. <br>
7.81% from 384 customers or 30 customers are grouped into **Best Customers**. In this segment the customers recently orders, has a high order frequency and a high total order too. <br>
0.52% from 384 customers or 2 customers are grouped into **Almost Lost**. In this segment the customer recently orders but the order frequency and total of orders is low.

# Result
- In **2011** total order reach out around 484.26K, then in **2012 it decreased** up to 2.83% so that there were only around 470.5K total products order. Meanwhile, in **2013 there was an increase** in orders reach out around 29.31% or total order up to 608.47K and in **2014 also an increase** of 20.63% so that the total order product reach out around 734K.
- In **2011**, total orders around **484.26K**, which the **highest orders** occurred in September 2011 with growth up to **193.03%** meanwhile the **lowest orders** occurred in February 2011 with a decrease up to **65%**. 
- In **2012** total orders around **470.5K**, in this year (2012) there was a 2.8% **decrease** in orders.  Which the **highest orders** occurred in March 2012 with growth up to **215.04%** meanwhile the **lowest orders** occurred in January 2012 with a decrease up to **73.87%**.
- In **2013** total orders around **608.47K**, in this year (2013) there was a 29.31% **increase** in orders.  Which the **highest orders** occurred in March 2013 with growth up to **215.04%** meanwhile the **lowest orders** occurred in January 2013 with a decrease up to **75.25%**. 
- In **2014** total orders around **734K**, in this year (2014) there was a 20.63% **increase** in orders.  Which the **highest orders** occurred in March 2014 with growth in orders of **165.77%** meanwhile the **lowest orders** occurred in January 2014 with a decrease up to **54.02%**. 
- The **highest total** orders from 2011 to 2014 occurred in November and December, while the **lowest total** orders from 2011 to 2014 occurred in January and February.
- On three days at the beginning of the month, **1st and 3rd date** there was an **increase** in orders. Also in the middle of the month, which is on the 15th to 18th, there is also an increase in orders. Meanwhile on W4 which is the **24th to the 30th** there is a **decrease** in orders.

# Recommendations
We give recommendations for each segment. First, we recommend to **Loyal Customer** segment to maintain the engagement, increase the recency and monetary with create a program like loyalty points that increase purchase, giving customers cashback or free shipping voucher, make sale program when big event such as christmas, new year, black friday, etc. Offering product with expensive prices that they might want to buy. <br>
Second, we recommend for **Big Spenders** segment to increase the loyalty by making loyalty points program, the points can be exchange with reward or other benefit, offering budling product that Big Spenders customers may like, that buy 2 or more product in package is cheaper than the total price every item combined. <br>
Third, we recommend for **Lost Cheap** Customer segment, that this segment customers is churn. So, better focus on acquiring new customers. <br>
Then, for **Lost Customer** segment in the verge of churn, decrease this segment by recommend things on sale that they buy in the past and focus on acquiring new customers. <br>
And then for **Best Customer** segment to increase this segment by offering products they like, purchased, and sale. Making loyalty points program, the points can be exchange with reward or other benefit that only Best Customer can get, such as different cashback and free shipping voucher than other customers. <br>
The last, for **Almost Lost** segment, business team can increase frequency by recommend things that they may like or purchased and on sale. Giving them free shipping voucher with non-minimum purchase.
