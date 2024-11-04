# CAPSTONE-PROJECT-DOCUMENTATION-2

----

## PROJECT TITLE: CAPSTONE CUSTOMER DATA

----

[PROJECT OVERVIEW](#project-overview)

[DATA SOURCES](#data-sources)

[TOOLS USED](#tools-used)

[DATA CLEANING AND PREPARATIONS](#data-cleaning-and-preparations)

[EXPLORATORY DATA ANALYSIS](#exploratory-data-analysis)

[DATA ANALYSIS](#data-analysis)

[DATA SUMMARIZATION](#data-summarization)

[DATA VISUALIZATION](#data-visualization)

[INFERENCES](#inferences)

[CONCLUSION](#conclusion)

----

### PROJECT OVERVIEW
This project aims at analyzing the for a subscription service to identify 
segments and trends. My goal is to understand customer behavior, track subscription types, 
and identify key trends in cancellations and renewals. Then finally a Power BI 
dashboard that presents your analysis.

----

### DATA SOURCES
The primary source of data used in the projects are data.sales.cv and this is an open source data that can be freely downloaded from open source online such as kaggle or FRED or any other data respository site.

----

### TOOLS USED
- Microsoft Excel [Download Here](https://www.microsoft.com) 
   1. For Data cleaning
   2. For Data Analysis
   3. For Data visualization

- SQL - Structured Query Language for Quering of Data
  
- Power Bi
  
   1.business analysis
  
   2.visualization
  
   3.creating intereative dashboard.
  
- GitHub for Portfolio Building
      
----

### DATA CLEANING AND PREPARATIONS
In the initial phase of the data cleaning and preparation, the following actions was performed;
   1. Data loading and inspection
   2. Handling missing variables
   3. Data cleaning and formatting
   4. Removing duplicate

----

### EXPLORATORY DATA ANALYSIS
This analysis is meant to answer the followimg questions:
   - The Total Sales Performance
   - Total sales generated in each region
   - Subscrption trends
   - Sales performance by subscription type
   - Rate of cancellation and renewal


----

### DATA ANALYSIS

##### EXCEL FUNCTIONS USED FOR ANALYSIS

````
Total Revenue =SUM(H2:H33788)
````
````
Average Revenue =AVERAGE(H2:H33788)
````
````
Total Number of Customers =COUNTA(G2:G33788)
````
````
Count of customers that cancelled =COUNTIF(G2:G33788,G33769)
````
````
Count of customers that did'nt cancel =COUNTIF(G2:G33788,G33768)
````

- MOST POPULAR SUBSCRIPTION TYPE
````
Count for Basic =COUNTIF(D2:D33788,D33771)
````
````
Count for Premuim =COUNTIF(D2:D33788,D33768)
````
````
Count for Standard =COUNTIF(D2:D33788,D33769)
````


##### SQL QUERIES USED FOR THE ANALYSIS

````
select * from [dbo].[Customer Data(capstone project)]
````
````
Select  region, count(distinct Customerid) as total_customers 
from [dbo].[Customer Data(capstone project)]
Group by region;
````
````
Select top 1 subscriptiontype, count(distinct customerid) as total_customers
From[dbo].[Customer Data(capstone project)]
Group by subscriptiontype 
Order by total_customers desc;
````
````
Select CustomerID, datediff(month, subscriptionstart, subscriptionend) As Subscription_duration, Canceled
from [dbo].[Customer Data(capstone project)]
where DATEDIFF(month, subscriptionstart, subscriptionend) < = 6
````
````
 Select avg(datediff(month, subscriptionstart, subscriptionend)) as avg_subscription_duration
From[dbo].[Customer Data(capstone project)]
````
````
 Select customerid, datediff(month, subscriptionstart, subscriptionend) As Subscription_duration, Canceled
From[dbo].[Customer Data(capstone project)]
Where datediff(month, subscriptionstart,  subscriptionend) > 12;
````
````
Select subscriptiontype,
Sum(revenue) as total_revenue 
From[dbo].[Customer Data(capstone project)]
Group by subscriptiontype;
````
````
Select top 3 region, 
Count(*) as Canceled_count
From[dbo].[Customer Data(capstone project)]
Where Canceled = 1
Group by region
Order by region Asc;
````
````
select count(canceled) As Canceled_subscription
from[dbo].[Customer Data(capstone project)]
where Canceled = 1
````
````
select COUNT(canceled) As Active_Subscription
from[dbo].[Customer Data(capstone project)]
where Canceled = 0
````


### DATA SUMMARIZATION

##### PIVORT TABLES
- Pivort tables was used to summarize the data.

