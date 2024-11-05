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
Pivort tables was used to summarize the data.

- REGION BY REVENUE

  ![image](https://github.com/user-attachments/assets/2f58413e-c0ac-4e39-8336-a718011df4b6)

- SUBSCRIPTION TYPE BY REVENUE

  ![image](https://github.com/user-attachments/assets/0573f070-0829-4970-ac24-ed2baa8b947a)

- COUNT OF CANCELLED BY SUBSCRIPTION TYPE

 ![image](https://github.com/user-attachments/assets/f3da8ba1-839e-4347-bd99-b236a6bb4b1b)

 - SUBSCRIPTION TYPE BY AVERAGE SUBSCRIPTION DURATION

  ![image](https://github.com/user-attachments/assets/253a4653-ec99-4c95-bd10-e369b5b314c2)


  ### DATA VISUALIZATION

- CUSTOMER DATA TABLE SHOWING APPLIED STEPS
  
  ![image](https://github.com/user-attachments/assets/565c2b5a-3dbb-4503-9c07-499fb26a8056)

- CUSTOMER DATA DASHBOARD

![image](https://github.com/user-attachments/assets/58a9201d-8dee-47c4-b24e-881c932c6bd2)


##### FILTER BY REGION

- EAST

![image](https://github.com/user-attachments/assets/e2beb9be-a6e9-4ced-8b7e-783af43a0f8f)

- NORTH

![image](https://github.com/user-attachments/assets/0f85b75c-cc85-475a-a859-091e7f102e9f)

- WEST

![image](https://github.com/user-attachments/assets/de4b4859-c09d-4ba5-b8f4-612db07f3235)

- SOUTH

![image](https://github.com/user-attachments/assets/9727051c-4bdc-4859-bee8-a0f085cb9e94)


##### FILTER BY SUBSCRIPTION TYPE

- BASIC

![image](https://github.com/user-attachments/assets/25a5dc5d-2a47-4307-87a4-8f7552708826)

- STANDARD

![image](https://github.com/user-attachments/assets/cee8343f-85c0-49fc-aa12-37a4a918e8e1)

- PREMIUM

![image](https://github.com/user-attachments/assets/e2dde8a8-8564-4af8-a6c4-93d87e24595d)


### INFERENCES

- OVERALL PERFORMANCE: The total sum of revenue was Sixty-seven Million, Five Hundred anf forty Thousand , One Hundred and Seventy-five. The count of canellation is Fifteen Thousand, One Hundred and Seventy-five, this means withe the out of the total customer which is Thirty-three Thousand,Seven Hundred and Eighty-seven, Fifteen Thousand, One Hundred and Seventy-five canceled leaving Eighteen Thousand, Six Hundred and Twelve as count of renewed customers. This means the number of renewed customer is greater than the number of canceled cvustomer.

- CANCELLATION BY REGION

1. EAST: The East having a total sum of revenue of Sixteen Million, Nine Hundred and Fifty-eight Thousand, Seven Hundred and sixty-three, Total number of customers of eight Thousand Four Hundred and Eighty-eight has no count of cancellation. This means that the customers at the East renewed their subscription.

2. NORTH: The North having a total sum of revenue of Sixteen Million, Eight Hundred and Seventeeen Thousand, Nine Hundred and Seventy-two, Total number of customers of eight Thousand Four Hundred and Thirty-three has count of cancellation of Five Thousand and Sixty-seven. This means that Five Thousand and Sixty-seven customers did not renew their subscription.

3. WEST: The West having a total sum of revenue of Sixteen Million, Eight Hundred and Sixty-four Thousand, Three Hundred and Seventy-six, Total number of customers of eight Thousand Four Hundred and Twenty has count of cancellation of Five Thousand and Fourty-four. This means that Five Thousand and Fourty-four customers did not renew their subscription.

4. SOUTH: The South having a total sum of revenue of Sixteen Million, Eight Hundred and Nienty-nine Thousand, Sixty-four, Total number of customers of eight Thousand Four Hundred and Fourty-six has count of cancellation of Five Thousand and Sixty-four. This means that Five Thousand and Sixty-four customers did not renew their subscription.

- CANCELLATION BY SUBSCRIPTION TYPE

1. BASIC: The basic subscription type has the sum of total revenue as Thirty-three Milllion, Seven Hundred and Seventy-six Thousand, Seven Hundred and Thirty-five. The total number of customers using the basic subscription type is Sixteen Thousand, Nine Hundred and Twenty-one with the count of cancellation of Five Thounsand and Sixty-seven. This means that Five Thounsand and Sixty-seven of coustomers using the basic subscription type did not renew. This subscription type was used in the East and North region, this means it is not active in the south and west region.

3. STANDARD: The standard subscription type has the sum of total revenue as Sixteen Milllion, Eight Hundred and Sixty-four Thousand, Three Hundred and Seventy-six. The total number of customers using the standard subscription type is Eight Thousand, Four Hundred and Twenty with the count of cancellation of Five Thounsand and Foury-four. This means that Five Thounsand and Foury-four of coustomers using the standard subscription type did not renew. This subscription type was used only in the West region, this means it is not active in the south, east and north region.

4. PREMIUM: The premium subscription type has the sum of total revenue as Sixteen Milllion, Eight Hundred and Ninety-nine Thousand and Sixty-four. The total number of customers using the premium subscription type is Eight Thousand, Four Hundred and Fourty-six with the count of cancellation of Five Thounsand and Sixty-four. This means that Five Thounsand and Sixty-four of coustomers using the premium subscription type did not renew. This subscription type was used only in the south region, this means it is not active in the west, east and north region.



### CONCLUSION

In summary, The East region does not have any record of cancelled subscription. The Nort region has the highest number of cancellation. 
According to the total number of customers, Basic subscription type is the most popular and highest used subscription type.
I recommend that a customer survey should be carried out to know the reason why some customers in the North, south and West region cancelled their subscription. This will help to meet up with the customers expectations and desire which can led to low rate of cancellation.






 

