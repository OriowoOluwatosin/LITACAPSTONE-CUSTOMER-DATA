# LITACAPSTONE-CUSTOMERS-DATA

OUTLINE

PROJECT OVERVIEW:

DATA DESCRIPTION:

DASH BOARD REVIEW:

STATISTICS ABOUT THE DATASET:

METHODOLOGY:

DATA ANALYSIS:

DASHBOARD OVERVIEW WITH POWERBI:

INSIGHTS GENERATION:

RECOMMENDATION:

CONCLUSION:


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





