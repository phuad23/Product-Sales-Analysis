# Product Sales Analysis

### Project Overview
---
This data analysis project aims to provide insights into the sales performance of product of a company for the past 6 months. By analysing various approach of the sales method, we seek to identify trends, make data-driven recommendation and gain a deeper understanding of the product sales with each methods.

## Data Sources

Product Sales: The primary dataset used for this analysis is the "product_sales.csv" file, containing detailed information about the product sales of the company.

### Tools
- Jupyter Notbeook - Python - for Data Cleaning and Data Analysis
  -  [Download here](https://www.anaconda.com/download)
- Jupyter Notbeook - Matplotlib - for Data Visualization

### Data Cleaning/Preparation

  In the initial data preparation phase, we performed the following tasks:
  1. Importing and Data Loading,
  2. Handling missing values,
  3. Data cleaning and formatting,
  4. Data validation
  
### Exploratory Data Analysis (EDA)

EDA involves exploring the product sales data to answer key questions, such as;
- How many customers were there for each approach?
  
![sales_method_count](https://github.com/user-attachments/assets/68bbf473-c320-4fbe-b08a-ab6f9a3d6222)

- What does the spread of the revenue look like overall? And for each method?

![spread of revenue](https://github.com/user-attachments/assets/a9c75695-554f-4572-8508-401dc59c55ea)


- Was there any difference in revenue over time for each of the methods?

![revenue_by_time_method](https://github.com/user-attachments/assets/11823533-0b7c-4d29-88ba-cc27b0120758)

### Data Analysis

``` Python
#to know the number of customers for each approach
customer_approach_count= df['sales_method'].value_counts()
print(customer_approach_count)
```

``` Python
#What does the spread of the revenue look like overall? And for each method?
revenue_by_each_approach = df.groupby('sales_method')['revenue'].sum()
print(revenue_by_each_approach)
```

``` Python
# Was there any difference in revenue over time for each of the methods?
# Group the data by weeks and method, and calculate the total revenue for each group
grouped_df = df.groupby(['week', 'sales_method'])['revenue'].sum().reset_index()
print(grouped_df)
```

### Results/Findings
The analysis results are summarized as follows;
1. The Email sales method has the highest number of customer within the past 6months.
2. Since email sales method has the highest customer, therefore it also has the highest revenue.
3. There is difference in revenue over time because email has the highest revenue in the first month but later reduced as month goes  by. Email + Call method has the lowest revenue in the first month but the revenue increased as the month progress.

### Recommendations

Based on the analysis, i will recommend the following actions;
- Adopt the Email + Call method for increase in sales and revenue. 
- Focus more on the states with highest revenue, states like California, Texas, New York e.t.c
- The Email can still be used as a sales_method but it is only useful for a short period as the revenue decreases as times pass by.

### Limitations
I had to replace all the missing values in the revenue table with zero (0) because they would affect the accuracy of my conclusions from the analysis.

### Certification
- ![Data Analyst](https://github.com/user-attachments/assets/35da6fd6-4a0c-4243-84f0-880c5017bafc)
