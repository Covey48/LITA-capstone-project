# LITA-capstone-project
---

## PROJECT TITLE: SALES PERFORMANCE ANALYSIS FOR A RETAIL SORE
---

### PROJECT OVERVIEW
---
This project aims to analyze the sales performance of a retail store. I seek to explore the sales data to uncover key insights such as top-selling products, regional
performance, and monthly sales trends.

### DATA SOURCES
---
The source of this data was assigned by the facilitators of the LITA PROGRAM for the capstone project

### TOOLS USED
---
- SQL Structured Query Language for data entry, data querying and data cleaning 
- Microsoft Excel for data analysis, data validation and Data visualization 
- GitHub for Portfolio building
- Microsoft word for report writing
- PoweBi for data visualization and project reporting

### 	DATA CLEANING AND PREPARATION
---
In the Initial phase of Data cleaning and preparation, I performed the following actions;
1.  Data loading and inspection
2.  Handling missing variables
3.  Data cleaning and formatting
4. Removing duplicates
5. Data importation into SQL
6. Cleaned data importation into PowerBi
7. Data transformation using Power query editor

###  	EXPLORATORY DATA ANALYSIS
---
This involved the exploring of the data to answer some questions about the data such as;
- total sales by product, region, and month.
- the highest-selling product by total sales value.
- the  total revenue per product.
- the monthly sales totals for the current year.
- the top 5 customers by total purchase amount.
- the percentage of total sales contributed by each region.
- identify products with no sales in the last quarter.

###  DATA ANALYSIS
---
This is where I inputed some basic line of functions and queries like;

~~~
            MS EXCEL
    =AVERAGEIF(D2:D50001,D2,H2:H50001)
 =SUMIF(C2:C50001,C2,H2:H50001)
~~~

~~~
        SQL

select * from [dbo].[LITA CAPSTONE PROJECT 11]

SELECT Product, SUM (SalesPrice) AS TOTALSALES FROM [dbo].[LITA CAPSTONE PROJECT 11]
GROUP BY Product

SELECT Region, COUNT (SalesPrice) AS NoOfSalesTransactions FROM [dbo].[LITA CAPSTONE PROJECT 11]
GROUP BY Region

SELECT Product, MAX (SalesPrice) AS HighestSellingProduct FROM [dbo].[LITA CAPSTONE PROJECT 11]
GROUP BY Product
ORDER BY 2 DESC

SELECT OrderDate FROM [dbo].[LITA CAPSTONE PROJECT 11]
WHERE YEAR (OrderDate) in (2024) 

SELECT Month(OrderDate) AS Month, SUM(SalesPrice) AS MonthlySalesTotal
FROM [dbo].[LITA CAPSTONE PROJECT 11] WHERE YEAR(OrderDate) = 2024
GROUP BY Month(OrderDate)
ORDER BY Month

SELECT Top (5) Customer_Id,
 SUM(SalesPrice) AS TotalPurchaseAmount FROM [dbo].[LITA CAPSTONE PROJECT 11]
GROUP BY Customer_Id
ORDER BY 2 Desc

SELECT Region, SUM(SalesPrice) AS RegionTotalSales,
FORMAT(ROUND((SUM(SalesPrice) / CAST((SELECT SUM(SalesPrice) FROM [dbo].[LITA CAPSTONE PROJECT 11]) AS DECIMAL(10,2)) * 100), 1), '0.#') 
AS PercentageOfTotalSales
FROM [dbo].[LITA CAPSTONE PROJECT 11]
GROUP BY Region
ORDER BY 3 DESC

SELECT Product FROM [dbo].[LITA CAPSTONE PROJECT 11]
GROUP BY Product
HAVING SUM(CASE 
WHEN OrderDate BETWEEN '2024-06-01' AND '2024-08-31' 
THEN 1 ELSE 0 END) = 0
~~~

### DATA VISUALIZATION
------------
I used pivot tables and charts to summarize total sales by product, region, and month

![image alt](https://github.com/Covey48/LITA-capstone-project/blob/c843ff8a494391d8c300e1ae7919bfd12d3c2e98/Screenshot%20(10).png)

![image alt](https://github.com/Covey48/LITA-capstone-project/blob/6aa2c0e8eb1216c6943b5cadaa19b05eee9ad7b3/Screenshot%20(11).png)

![image alt](https://github.com/Covey48/LITA-capstone-project/blob/44fddc97fd3d4f6150fe1650491c407d17251a6c/LITA%20PICTURE%20POWERBI.png)

