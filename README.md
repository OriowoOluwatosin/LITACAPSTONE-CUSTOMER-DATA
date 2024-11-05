# LITACAPSTONE-CUSTOMERS-DATA

OUTLINE

[ PROJECT OVERVIEW: ](project-view)

[ DATA DESCRIPTION: ](data-description)

[ DASH BOARD REVIEW: ](dash-board-review)

[ STATISTICS ABOUT THE DATASET: ](statistics-about-the-dataset)

[ METHODOLOGY: ](methodogy)

[ DATA ANALYSIS: ](data-analysis)

 [ DASHBOARD OVERVIEW WITH POWERBI: ](dashboard-overview-with-powerbi)

[ INSIGHTS GENERATION: ](insight-generation)

[ RECOMMENDATION: ](recommendation)

[ CONCLUSION: ](conclusion)


### PROJECT OVERVIEW:
Making reference to the data and capstone project document shared earlier, by analyzing the customer data for subscription services to identify segments and trends.
This analysis helps to understand 
- customer behaviour
- track subscription type
- identify key trends in cancelation and renewal
Thereby, carrying out the following exploratory process of the subscriotion service to uncover key insights.

### DATA DESCRIPTION:

This dataset includes the following Columns:

CustomerID
CustomerName
Region
SubscriptionType
SubscriptionStart
SubscriptionEnd
Canceled
Revenue

### DASHBOARD REVIEW:

Customer Id

CustomerName

Region: The other regional branches of the store ( North, South, East West).

Subscription Type: The type of subscription that was subscribed (Basic, Premium, Standard).

Subscription Start: The day the subscription started.

Subscription End: The day the subscription ended.

Canceled: The cancellation of the subscription.

Revenue: The income of each subscription.

### STATISTICS ABOUT THE DATA:

- Number of Unique Customers: 33,787

- Subscription Type: 3

- Total Revenue: 67,540,175
  
- Total Region: 4

### METHODOLOGY:

#### Data Collection

LITA_ The Incubator Hub provided the dataset for this analysis for learning and training purposes. The data was provided in an Excel sheet [download Here].(https://canvas.instructure.com/files/273182802/download?download_frd=1) The Excel sheet made it accessible to analyze the Excel sheet The Excel sheet was further converted to CSV format for easy importing of files into:

SQL to write various queries

Power BI to create dashboards using various charts (PieChart and clustered Column Chart)

### DATA ANALYSIS:

#### Calculation in Excel

**Generating Subscription Duration**
(=F2-E2) SubDuration Customers data

![image](https://github.com/user-attachments/assets/9b82352c-8f4c-43b1-84d0-bf94c30406ed)

**calculating most popular subscription type**
=SUMIF($D1:$D33788,$D8,$H1:$H33788) Excel Customers Data

![image](https://github.com/user-attachments/assets/157fb044-b056-4970-97b1-9acdde6fcc78)


**Calculating average subscription duration**
=AVERAGE(I1:I33788) Excel Customers Data

![image](https://github.com/user-attachments/assets/1200022f-7cd9-49d2-a737-bc86cffe6c0b)

#### Excel Chart

Excel Customers Data 3 

![image](https://github.com/user-attachments/assets/6f058e38-9698-49a4-b2be-48872e5ecbdc)

Excel Customers Data 2

![image](https://github.com/user-attachments/assets/deadcb91-6856-4749-87b2-58ef598f2b4f)

#### Pivot Table

![image](https://github.com/user-attachments/assets/fd964476-e49a-4e42-8e60-2a8e1047943e)


#### SQL Queries

  1. select Region, count (CustomerID) as Region_customers from [dbo].[Customer data sec]
     GROUP BY Region
  2. select subscriptionType, count (CustomerID) as cust_subscription from [dbo].[Customer data sec]
     Group by SubscriptionType
     Order by cust_subscription desc
  3. SELECT *
     FROM [dbo].[Customer data sec]
     WHERE DATEDIFF(month, SubscriptionStart, SubscriptionEnd) <= 6
  4. SELECT AVG(DATEDIFF(month, SubscriptionStart, SubscriptionEnd)) AS average_duration
     FROM [dbo].[Customer data sec]
  5. SELECT customerid, subscriptiontype, SubscriptionStart, SubscriptionEnd
     FROM [dbo].[Customer data sec]
     WHERE DATEDIFF(month, SubscriptionStart, SubscriptionEnd) > 12
  6. SELECT subscriptiontype, SUM(revenue) AS total_revenue
     FROM [dbo].[Customer data sec]
     GROUP BY subscriptiontype
  7. SELECT region, COUNT(*) AS canceled_sub
     FROM [dbo].[Customer data sec]
     WHERE canceled = 1
     GROUP BY region
     ORDER BY canceled_sub DESC
  
     SELECT region, COUNT(*) AS canceled_sub
     FROM [dbo].[Customer data sec]
     WHERE canceled = 0
     GROUP BY region
     ORDER BY canceled_sub DESC
  8.SELECT canceled, COUNT(*) AS total_subscriptions
    FROM [dbo].[Customer data sec]
    GROUP BY canceled


![image](https://github.com/user-attachments/assets/00f20e8a-d233-4957-b9fc-4f6c0ba1dfbc)



![image](https://github.com/user-attachments/assets/9714605d-ee3e-4991-97ef-64479c3a789b)


![image](https://github.com/user-attachments/assets/6b1900fa-81e8-4787-9cbb-e2c1b9436add)


![image](https://github.com/user-attachments/assets/b0cb146c-492f-4f0d-ad4a-f94071e22646)

DASH BOARD OVERVIEW WITH POWER BI:

![image](https://github.com/user-attachments/assets/7241d4ef-d440-43d9-9e43-c789860232d9)

### INSIGHT GENERATION:

**Insights on Revenue for Subscription Type**

Basic: This Subscription Type leads  as it generates more revenue, with 33,776,735.
This indicates potentially larger transaction values per sale. 
Giving a clear confirmation that customers prefer the Basic subscription type.
Premium: This Subscription has a bit low patronage with revenue 16,899,064, customers have low interest in this kind of subscription.
Standard: This subscription revenue is relatively close to premium with a revenue of 16,864,376, customers having interest in this subscription are almost that of premium.


### RECOMMENDATION


**Subscription Comparison:** Implement targeted marketing strategies, campaigns, adverts and sensitization to create more awareness about premium and standard subscriptions.
A discounted price should be tagged on the other subscription type packages(premium and standard).

Also,make the benefits known to the customers especially to curate more sales and generate more revenue


**Subscriptions Optimization:** Make the most effective use of the subscription trend by making basic subscriptions more available.
Rebraning of Premium and Standard subscription type to fit duly into the market and target influential,luxurious and decadent customers who are always ready to spend on luxury.

### CONCLUSION

Premium and Standard subscriptions need more focus and attention on

-boosting revenue through marketing strategies
-studying market trends within the region to adequately decode the highest-selling subscription type in the region.
-arousing the inquisitiveness of its target customers.


