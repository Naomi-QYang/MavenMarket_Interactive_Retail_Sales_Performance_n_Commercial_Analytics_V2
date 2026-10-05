# Maven Market Interactive Retail Sales Performance and Commercial Analytics
A Power BI analytics project analysing *sales performance, customer behaviour, product profitability and store performance* for a multi-national grocery retailer with stores across Canada, Mexico and the US.

⛏️**Tools:** Power BI | DAX & Visual Calculation | Power Query | Data Modelling | Time Intelligence | Business Analysis

## ⭐ Project Overview
This project is built on the Maven Market grocery retail dataset, designed to demonstrate how sales, customer, product and store data can be transformed into actionable commercial insights.

The report combines financial and commercial analysis with the objective of moving beyond descriptive reporting to identify the key drivers behind changes in *Sales, Customer behaviour, Products and Stores Performance* and to support *data-driven* decision making. It allows users to move from an executive-level view into detailed store, product and customer analysis through interactive slicers, dynamic measures and drill-through functionality.

## 🎯 Business Objectives
The report was developed to help managers answer 4 key questions:

***1. How is the business performing?***
 * How are sales performing across different time periods, regions and store channels?
 * How does current performance compare with the same period last year?
 * How are gross margin and return rate changing?
 * What are the key drivers behind sales growth/decline?
 * Which store channels and product categories contribute the most to overall sales?
 * How does sales performance change across YoY, QoQ and MoM periods?
 * What is the sales performing expected to be in the next 3 periods?

**2. What drives customer behaviour?***
 * Who are the most valuable and most active customers?
 * How many customers actively making transactions?
 * How many customers have returned after being inactive 90+days?
 * What proportion of customers make repeat purchases across different time period?
 * Is customer engagement improving or deteriorating?
 * How does Average Order Value change alongside customer and transaction growth during weekday and weekend?

***3. Where are the commercial opportunities and risks?***
 * Which kind of products contribute the most and at the same time move fast?
 * Which kind of products are growing/decling?
 * How many product SKUs is actively selling, compared with the number of products SKUs lost sale, across different time periods?
 * Which products have higher return rates while low sales?
 * Which product SKUs/Categories are frequently purchased together? And which product combinations have the strongest affinity?

## 🛠️ Key Techniques
The report was built by using the following tools and technologies:
 * 💭 **Power BI Desktop:** Main business intelligence platform used for report creation which includes connecting, modelling, aggregating and visualising data
   - 🔍*Power Query* - Data transformation and cleaning process for extracting, cleaning and shaping data to prepare it for modeling and analysis
   - 🔗*Data Modeling* - Relationships established among fact tables (transactions and returns) and dimension tables (calendar, customers, products, stores and regions) to enable cross-filtering and accurate calculation
   - 🧠*Data Analysis Expressions (DAX)* + *Visual Calculations* - used for creating supporting tables, grouping and aggregating data, dynamic visuals and conditional logic
   - ⚙️*Parameters* - let users to dynamically update measures inputs to see the impact on a visual or change the metrics/dimensions shown in a visual
   - 📈*Tooltips* - hiddden custom information to be shown against the hovered product name
   - 🧐*Report Interactions* - an interactive analytical experience with drill-through, cross-visual interactions, bookmarks and page nagvigation

 * 🕵️ **Key Analytical Methods:**
   - 🏆*Top/Bottom N Analysis* - identify highes/lowest performing stores, products or categories
   - 📅*Time Intelligence* - analyse business growth trends to support performance evaluation and decision-making. It allows users to switch between Year, Quarter and Month on the <ins>Executive Dashboard</ins> page, and between Last 8 Quarters (quarter granular), Last 12 Months (month granular), Last 13 Weeks (week granular) and Last 30 Days (day granular) on the detailed <ins>Customers, Products and Stores</ins> pages.
   - ⚖️*Pareto Analysis* - identify product categories/store types that drive the majority of sales (opportunity) / returns (risks), supporting more targeted resource allocation and performance management
   - ✨*BCG-Style Matrix* - identify products that are strong performers, stable revenue contributors, growth opportunities or potential underperformers, by <ins>Growth Rate X Sales Contribution</ins> with a percentile slicer to control the classification boundaries interactively
   - 🛍️*Basket Analysis* - analyse product affinity and co-purchase behaviour to identify potential cross-selling opportunities and support sales strategies planning

## 💾 Data Source
This data is from Maven Market, a multi-national grocery chain with locations in Canada, Mexico and the US, including daily transactions data and returns data, details on their 10,281 customers, 1,560 products and 24 stores.

<a href="https://www.udemy.com/course/microsoft-power-bi-up-running-with-power-bi-desktop/?couponCode=26BBPAA2MX"> Data Source </a>

***Date Transformation:***
The original data of Transaction and Returns covers the period from *<ins> 1 January 1997 </ins>* to *<ins> 31 December 1998 </ins>*. The date fields is shifted and extended to cover from *<ins> 1 January 2024 </ins>* to *<ins> 31 December 2025 </ins>* across fact and dimension tables to align the dataset with the current reporting period and enable realistic relative-date calculations.

**Transaction Definition:***
The transaction table does not contain a transaction/order ID. A order ID is created on each transaction line in the format of "**C**[5 digits Customer ID]**S**[2 digits Store ID]**D**[8 digits date in DDMMYYYY]". Therefore, transaction lines made by the same customer at the same store on the same date are assumed to be in the same transaction for the purpose of transaction-based analysis.

***Product Categorisation:***
The original product data does not contain product category information. A product hierarchy was therefore created by:
 - Extracting product names from the full product name by removing the product brand to consolidate 1,560 unique product full names into 311 unique product names
 - Creating a new table via Power Query with 311 distinct product names
 - Manually creating a mapping list with keywords and the according product subcategory
 - Assigning each product name to its relative subcategory according to the mapping list
 - Grouping subcategories into main categories

## 📊 Report Structure
 * **Executive Summary:** intentionally designed as the entry point into the detailed analysis page. The objective is designed to help decision-makers quickly identify <ins>what happened</ins> and <ins>where did it happen</ins>.
   - *Overview* - provides a high-level overview of business performance in the latest period (year/quarter/month)
   - *Sales Performance* - provides a detailed-level sales performance movement over year/quarter/month
 * **Customers Analytics:** focuses on customer activity, engagement and lifetime value. One of the key analytical areas is to identify inactive, one-off reactivated, successfully reactivated and dormant customers by using a 90-day customer activity framework. This enables the report to move beyond simple customer counts and investigate customer retention and re-engagement opportunities.
 * **Product Performance:** supports dynamic time-period analysis using selectable time granularities and rolling periods.
   - *Trend* - analyses the performance on each product SKUs and product categories from both sales and profitability perspectives, and classifies product categories/brands into ⭐**Star**, 🐄 **Cash Cow**, ❓ **Question Mark** and 🐕 **Dog** which driven by Sales contribution, Growth Rate and user-selected percentile thresholds. This allows users to explore how the product portfolio changes under different assumptions.
   - *Comparison* - compare performance against same period last year, product categories, and combination of each set of product categories
   - *Basket Analysis* - analyses product subcategories/main categories frequently purchased together to identify potential product associations, which can be used to identify potential opportunities for cross-selling, product bundling and promotional planning.
 *  **Store Performance:** evaluates performance across individual stores, regions and store types/channels. This helps identify high-performing locations, underperforming stores and potential operational differences across store types and regions.

## ⚠️ Data Assumptions & Limitations
The report and Measures includes several assumptions that should be considered when interpreting the results

 * **Dates -** The <ins>Fact Tables</ins> were originally dated in 1997 and 1998. Dates were shifted forward to create a *2024-2025* analytical period. Dates on <ins>Dimension Tables</ins> were also adjusted where necessary to align them with the analysis period.
 * **Transactions ID -** Transaction lines made by the same customer at the same store on the same date are assumed to be in the same transaction.
 * **Product Categories -** The dataset does not provide a formal product category hierachy. Product subcategories is created by extracting keywords from each product name and then looking up its corresponding categories on the mapping list
 * No transaction or return data exists for All <ins>Mexico</ins> and <ins>Canada</ins> regions in 2024. Therefore, some YoY growth rate and comparisons may be distorted and should be interpreted with caution.
 * **Returns -** The returns table does not contain a transaction/order ID or customer ID. Therefore, each return records cannot be directly linked back to the original customer purchase. Returns are then analysed at the available date, product and store level. In addition, as there are no information for how to deal with each return, all returned products are assumed to be back to inventory and make available for resale. No additional adjustment or analysis is made for damaged, defective, or unsellable returned products. 
 * **Customer Lifecycle -** The available customer data does not provide the information of newly registered customers during the analysis period. Therefore, the analysis focuses on observed customer activity and reactivation rather than attempting to calculate a complete new-customer acquisition funnel.
 * **Product Pricing -** The analysis primarily uses the available retail price information. A more complete pricing dataset containing actual transaction prices, promotions and discounts would enable more detailed price-volume-mis and promotion effectiveness analysis.

## 💡 Project Insights
 * **Regions:**
   - Sales trend shows only USA stores attended Nov25 Sales Promotion/Boost event (better performance - Higher MoM and YoY growth compared to previous months and year), while Sales in other regions wasn't shown an identifiable growth in November 2025.
 * **Customers:**
   - *The customer base* is primarily driven by lower-income, childless consumers; however, their product preferences show no discernible pattern or clear trends
   - *Low income* customers (~55%) contributing more sales than customers in other income groups.
   - More Customers with *Bronze* membership (~55%) were buying products between 2024 and 2025. Customers who buying products with *Normal* membership occupied a larger portion in Low income group (~40%) than other groups (Medium 4.88% High 4.37%), while the largest portion of customers in Low income group buying products is with *Bronze* membership.
   - Customers with no children (60%+) at home are more likely to buy products compared to those with children.
 * **Products:**
   - Product brands contributing top 5 sales revenue in the analytical period are *Hermanos*, *Tell Tale*, *Ebony*, *Tri-State* and *High Top*, which are Suppliers of <ins>Vegetables</ins>, <ins>Nuts</ins> and <ins>Fruits</ins>.
   - The range of Gross Margins among each product falls between *48.51%* and *69.97%* from 2024 to 2025.
 * **Stores:**
   - North West Region (48%) contributed the most sales revenue in the analytical period, while received the most return requests (47%).
   - *Supermarket* and *Deluxe Supermarket* is contributing the most sales revenue (80%+) in the analytical period, highlighting these formats as key revenue drivers and potential areas of focus for future business planning.

## 🙌Recommendations
 * **South West** Region experienced declining Sales and Customers number, accompanied by an increasing return rate.
   - Engage with locat store managers an analyse customer feedback, returns and product-level sales to identify potential drivers such as service issues, product dissatisfaction or product availability.
   - Address identified service or operational issues and reassess product assorment to better align with customer demand.
   - Track customer retention, sales recovery and return rate to evaluate the effectiveness of the actions.
 * **CDR Grape Jelly** recorded no sales or returns during the analysis period, indicating a potential product availability, listing, or demand issue that needs further investigation.
   - Investigate whether the product is actively stocked and available for sale, to determine whether lacks of transactions reflects limited availability, discontinued status, data issues or weak customer demand, before assessing underlying customer demand.
   - If the product has been discontinued, coordinate with the <ins>IT</ins>/<ins>Data</ins> team to deactivate it in the product master data, for maintaining data integrity and prevent discontinued products from distorting active product and assortment analysis.
   - If the product is available but consistently generates no sales, reassess its relevance to customer demand, promotion plans to accelerate the sale before the expired date, and future sales plans on its pricing, positioning or product assortment.
 * No transaction & return data in 2024 was observed for All **Mexico (central, south, east)** regions and **Canada West** region, despite the relevant stores having been opened or remodelled before 2024. This suggests a potential data completeness issue that should be investigated before drawing conclusions about yealy business performance.
   - Escalate the issue to the <ins>IT</ins>/<ins>Data</ins> team to validate the 2024 transaction & return data pipeline
