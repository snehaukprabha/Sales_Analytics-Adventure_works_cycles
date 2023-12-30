# Sales_Analytics-Adventure_works_cycles
Adventure Works Cycles, is a large, multinational manufacturing company which manufactures and sells metal and composite bicycles to North American, European and Asian commercial markets. This project conduct a thorough market analysis using **Power BI**.

## Contents 
- Overview
- Objectives 
- Data Sources 
- Tools 
- Data Preparation 
	- Cleaning
	- Modelling
	- Transformation
- Exploratory Data Analysis
- Dashboard
- Insights and Recommendations
- Power BI files


## Overview
Adventure Works Cycles,  is a large, multinational manufacturing company. 
The company manufactures and sells metal and composite bicycles to North American, European and Asian commercial markets. While its base operation is in Bothell, Washington with 290 employees, several regional sales teams are located throughout their market base.

In 2000s, Adventure Works Cycles bought a small manufacturing plant in Mexico. Which manufactures several critical subcomponents for the Adventure Works Cycles product line. These subcomponents are shipped to the Bothell location for final product assembly. In 2001, this manufacturing plant became the sole manufacturer and distributor of the touring bicycle product group.
Coming off a successful fiscal year, Adventure Works Cycles is looking to broaden its market share by targeting their sales to their best customers, extending their product availability through an external Website.

## Objectives
1. Conduct a thorough market analysis to identify and target the most valuable customers.
2. Identify the most profitable market and enhance product accessibility through the establishment of an external e-commerce platform


## Data Sources
The analysis is based on data extracted from seven Excel files, encompassing 
- FactInternetSales (/data_set/FactInternetSales.xlsx) 
- DimCustomer (/data_set/Dimcustomer.xlsx)
- DimDate (/data_set/DimDate.xlsx)
- DimProduct (/data_set/DimProduct.xlsx)
- DimProductCategory (/data_set/DimProductCategory.xlsx)
- DimProductSubcategory (/data_set/DimProductSubCategory.xlsx)
- Dimsalesterritory (/data_set/DimSalesterritory.xlsx)
  
The data spans from December 2010 to January 2014.  
 The dataset utilized for this analysis was provided by the [ExcelR Solutions](https://www.excelr.com/) as part of an internship project



## Tools
- PowerBI

## Data Preparation
### Data Cleaning
The data cleaning process was executed using Power Query Editor and involved several operations mentioned below to ensure data accuracy and consistency:
- Union of tables through append queries.
- Correction of data types to ensure accurate representation.
- Elimination of empty and insignificant columns for streamlined analysis.
- Removal of empty rows for a more concise dataset.
- Cross-field validation to verify relationships between different fields for data consistency.
- Derivation of profit through a calculated column
- Addition of a custom column for customer full names using Power Query formula below  

	`Customer_fullname = Text.Combine({[FirstName], [MiddleName], [LastName]}, " ")`

### Data Modelling
Organized the data set and create data model in Model view.
-Data Model  

![Data_model](https://github.com/snehaukprabha/Sales_Analytics-Adventure_works_cycles/assets/146762387/fc6bb388-7f5a-40cb-86ca-73e0ed87a793)



### Data Transformation

Generate a calculated field in Power BI using DAX by leveraging existing fields. 

Example, Calculate the age of Customer at the time of placing order by using birth date from Customer table and order date from the Sales table. 

`Age at order = DATEDIFF(RELATED(DIMCUSTOMER[BirthDate]),Total_sales[OrderDate],YEAR)`
		
Also used Supplementary DAX expressions, like weekday, weeknum, and if statements to generate calculated columns.   
DAX measures such as Sameperiodlastyear, Rankx, Calculate, Count, Sum etc. are used for further analysis.

## Exploratory Data Analysis 
Adventure Works offers a diverse product range of 606 items for sale across 6 countries, encompassing 4 main categories and 37 subcategories. Over the period from December 2010 to January 2014, customers purchased a total of 60,398 products, contributing to an overall sales amount of 29.36 million dollars, with a corresponding profit of 9 million dollars. The profit margin achieved during this period stands at 30.65%. The customer base comprises a total of 18,484 individuals. The cumulative production cost for these products is recorded at 17.28 million dollars.
	
1. **Yearly, Quarterly, and Monthly Sales and Profit Trends:**  
   	   The depicted chart illustrates Adventure Works' consistent sales growth from 2010 to 2014, reaching a peak in Q4 2013. A notable decline occurred in 2012, mainly attributed to reduced sales in Q2, possibly influenced by the emergence of a competitive force offering enhanced customer opportunities. Each year consistently sees a sales peak in the fourth quarter, likely due to festive season demand.
   
    ![Yearly, Quarterly, and Monthly Sales and Profit Trends](https://github.com/snehaukprabha/Sales_Analytics-Adventure_works_cycles/assets/146762387/39bd9851-d75e-4ba0-8583-56ee514e4bd7)




2. **Weekday vs. Weekend Sales Distribution:**  
	   Analysis reveals that weekend sales constitute 28.2%, whereas weekday sales dominate at 71.8%. This suggests a preference for online shopping during work breaks or after work hours on weekdays.

    ![Weekday vs. Weekend Sales Distribution](https://github.com/snehaukprabha/Sales_Analytics-Adventure_works_cycles/assets/146762387/0ab05764-39a3-4736-bee3-7b17e0cbb33d)

	   
	
3. **Country-wise Sales Breakdown:**  
	   The United States leads in sales, contributing 31.98% of the total, followed by Australia at 30.86%. Canada lags behind with a modest 6.74% of total sales.

    
   ![Country-wise Sales Breakdown](https://github.com/snehaukprabha/Sales_Analytics-Adventure_works_cycles/assets/146762387/dbc3744a-dbf7-48cd-a71b-1ae0c11bc9e8)

  

4. **Categorywise Revenue Breakdown:**  
	   Bikes category emerge as the primary revenue driver, accounting for 96.46% of total revenue, with Accessories and Clothing contributing 2.39% and 1.16%, respectively.

  
     ![Categorywise Revenue Breakdown](https://github.com/snehaukprabha/Sales_Analytics-Adventure_works_cycles/assets/146762387/15bacbb4-8262-4ad5-a4f6-5d64a53534d1)



5. **Age Group Impact on Sales:**  
	   Customers aged 31 to 40 and 41 to 50 significantly contribute to revenue, generating $11.36 million and $8.17 million, respectively. Conversely, customers above 70 contribute less than $1 million.

   
     ![Age Group Impact on Sales](https://github.com/snehaukprabha/Sales_Analytics-Adventure_works_cycles/assets/146762387/4b1b222c-f93e-495d-a82e-ca27dee6dd2a)
 
	  
	
6. **Top N Customers and Revenue Generation:**  
	   Utilizing a parameterized visual, the company can identify top customers based on sales amount, enabling targeted benefits to enhance their contribution. Nichole Nara emerges as the top revenue contributor.

    
    ![Top N Customers and Revenue Generation](https://github.com/snehaukprabha/Sales_Analytics-Adventure_works_cycles/assets/146762387/41c47ca0-718b-491d-81f8-e475c9831ae8)
 
	  
	
7. **Gender-based Sales Equality:**  
	   Both male and female customers equally contribute to company revenue, with sales amounts of $14.55 million and $14.81 million, respectively.
   
    ![Gender-based Sales Equality](https://github.com/snehaukprabha/Sales_Analytics-Adventure_works_cycles/assets/146762387/9e09f929-e219-475f-872f-6c3b6d50f4ac)
 
	  
	
8. **Commute Distance Impact on Sales:**  
	   Customers with shorter commute distances (0-1 miles) significantly drive sales, while those with distances between 2-10 miles contribute half of the sales value. Customers with distances exceeding 10 miles contribute less, potentially due to a preference for alternative transportation.

   ![Commute Distance Impact on Sales](https://github.com/snehaukprabha/Sales_Analytics-Adventure_works_cycles/assets/146762387/6724ac68-f3e8-4574-bd5d-e820fb02236f)
  
	   
	
	
9. **Sales Disparity Based on Marital Status:**  
	   Married individuals show a higher tendency to make purchases (51.73%) compared to single individuals (48.27%), This trend may be indicative of a connection between the act of cycling a pursuit known for its health benefits and eco-friendly nature and the shared values or recreational choices often associated with married life.

    ![Sales Disparity Based on Marital Status](https://github.com/snehaukprabha/Sales_Analytics-Adventure_works_cycles/assets/146762387/c3713ef4-0975-4b5d-815a-0d297e8e3144)
  

	
10. **Age Distribution and Order Frequency:**  
	    The histogram illustrates that customers aged 31-40 place the highest number of orders (21,000), followed by the 41-50 age group with 17,000 orders. Histogram is right skewed ,The probability of getting outliers above 70 is more but receiving orders from customers over the age 70 is notably low.

    ![Age Distribution and Order Frequency](https://github.com/snehaukprabha/Sales_Analytics-Adventure_works_cycles/assets/146762387/04ce2505-8aba-46f7-a4c2-bdc24f324617)
   
	
11. **Category-Subcategory(Drilldown) Impact on Sales and Profit:**  
	    Bikes, especially Road Bikes, Mountain Bikes, and Touring Bikes, contribute significantly to sales and profit. In Accessories, Tires and Tubes dominate, while in Clothing, Jerseys lead in revenue. The sales trend for Bikes shows consistent growth from 2010 to 2014.

    ![Categorywise_sales_profit](https://github.com/snehaukprabha/Sales_Analytics-Adventure_works_cycles/assets/146762387/ded9c8de-6a98-4378-a406-8c244d5e7657)
    ![Subcategorywise_sales_profit](https://github.com/snehaukprabha/Sales_Analytics-Adventure_works_cycles/assets/146762387/83356c3c-4803-43ec-8238-b288781c098d)

  
	
	
12. **Sales Based on Model and Color Preferences:**  
	    The top 3 most popular bicycle models include Mountain-200 in Black and Silver, Road 150 in Red, and Road 250 in Black and Red respectively. This highlights a discernible inclination among customers for particular models and color combinations.  
The highest revenue-generating product is the Mountain-200 Black, contributing a substantial 4.03M in sales, signifying its strong market appeal and customer preference.

    ![Sales Based on Model and Color Preferences](https://github.com/snehaukprabha/Sales_Analytics-Adventure_works_cycles/assets/146762387/0198cd5c-a040-432f-8d66-69aab684b652)

	
	
13. **Model wise Correlation between Sales and Profit**   
	A correlation factor of 0.9 between model-wise sales and profit indicates a very strong positive correlation.
	This means that there is a highly consistent and positive relationship between the sales and profit of the different models. This suggests that as sales for a particular model increase, the profit generated from that model also tends to increase, and vice versa.

    ![Model wise Correlation between Sales and Profit](https://github.com/snehaukprabha/Sales_Analytics-Adventure_works_cycles/assets/146762387/231c8d2e-c37a-435d-bd76-9809b3d44282)
    
## Dashboard

![Home](https://github.com/snehaukprabha/Sales_Analytics-Adventure_works_cycles/assets/146762387/72e5318b-2e1e-41a6-9ce6-f0cbe5eb6a54)  

![Sales_analytics](https://github.com/snehaukprabha/Sales_Analytics-Adventure_works_cycles/assets/146762387/bc20a088-3ec7-4823-ba2c-4c06651136a3)  

![Customer_analytics](https://github.com/snehaukprabha/Sales_Analytics-Adventure_works_cycles/assets/146762387/668ce802-4493-4368-968c-2430efeafe49)  

![Product_Analytics](https://github.com/snehaukprabha/Sales_Analytics-Adventure_works_cycles/assets/146762387/a5fc20f0-d7c6-44e5-815e-c78a6ca2d89b)





## Insights and Recommendations

- Optimize Sales Strategies Based on Time Trends:
Leverage the consistent pattern of peak sales in the fourth quarter across the years, especially the significant peak in Q4 2013, to optimize inventory and marketing strategies. Plan for increased stock and promotional activities during this period. Additionally, analyse the sales dip in 2012, particularly in Q2, to understand the causes and develop strategies to mitigate similar declines in the future. This approach should include year-round vigilance and adaptability to maintain sales momentum throughout the year, capitalizing on identified peak times
	
- Diversify Geographical Focus:
	 Explore opportunities to expand market share in regions with lower sales, such as Canada. Tailor marketing strategies to address the specific needs and preferences of these regions.
- Strategic Promotion of Accessories and Clothing: 
	Given the dominance of bike sales, strategically promote accessories and clothing to diversify revenue streams. Highlight the unique features and benefits of these products to attract customer interest
- Customer Loyalty Programs:
	 Implement customer loyalty programs to further engage top customers, like Nichole Nara. Recognize and reward their contribution to encourage continued loyalty and increased spending
- Enhanced Product Visibility for Road Bikes:
	 Given the significant contribution of Road Bikes to sales and profit, ensure prominent visibility and promotion of this category. Highlight the features that make Road Bikes popular among customers to drive continued growth in this segment
- Personalized Marketing for Age Groups:
	Customize marketing communications and promotions to align with the preferences of key age demographics, notably targeting customers aged 31 to 50. This tailored approach aims to increase engagement and boost sales within these influential age segments.
- Focus on High-Performing Models:
	Concentrate resources, marketing efforts, and inventory management on the models that have demonstrated both high sales and high profitability. This targeted approach can maximize returns and ensure efficient resource allocation

## Power BI files
Uploaded here PowerBi/ADV_WORK_POWERBI.pbix

