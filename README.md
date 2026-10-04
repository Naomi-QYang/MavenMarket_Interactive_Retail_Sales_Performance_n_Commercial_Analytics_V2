# MavenMarket_Retail_Sales_Performance_Analytics_Version2
A Power BI portfolio project analysing *sales performance, customer behaviour, product profitability and store performance* for a multi-national grocery retailer.

⛏️**Tools:** Power BI | DAX & Visual Calculation | Power Query | Data Modelling | Time Intelligence | Business Analysis

## ⭐ Project Overview
This project analyses the performance of Maven Market, a multi-national grocery chain with stores across Canada, Mexico and the US.

The report was designed from a FP&A and commercial analytics perspective, with the objective of moving beyond descriptive reporting to identify the key drivers behind changes in *Sales, Customer behaviour, Products and Stores Performance*. It allows users to move from an executive-level view into detailed store, product and customer analysis through interactive slicers, dynamic measures and drill-through functionality.

## 🎯 Business Objectives
The report was developed to help managers answer 4 key questions:

***1. How is the business performing?***
 * How are sales, transactions trending?
 * How does current performance compare with the same period last year?
 * What is the driving changes in sales revenue?
 * How are gross margin and return rate changing?

***2. Which drivers contribute the performance?***
 * Which regions and store types contribute the most sales?
 * Which stores are outperforming or underperforming?
 * Which product brands generate the most sales revenue?
 * Which areas or anomalies require further investigation?

***3. What drives customer behaviour?***
 * How many customers actively making transactions?
 * What percentage of active customers made purchases more than 1 time?
 * How many customers have returned after being inactive 90+days?
 * Is customer engagement improving or deteriorating?
 * How does Average Order Value change alongside customer and transaction growth during weekday and weekend?

***4. Where are the commercial opportunities and risks?***
 * Which products generate high revenue and high margins?
 * Which products are slow-moving?
 * Which products have higher return rates while low sales?
 * Are changes in customer retention associated with changes in product returns?
 * Which stores, regions or products should be investigated further?

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
   - 🏆*Top/Bottom N Analysis* - identify highes/lowest performing stores, products or brands
   - 📅*Time Intelligence* - analyse business growth trends to support performance evaluation and decision-making
   - ⚖️*Pareto Analysis* - identify the store types that drive the majority of sales (opportunity) / returns (risks), supporting more targeted resource allocation and performance management

## 💾 Data Source
This data is from Maven Market, a multi-national grocery chain with locations in Canada, Mexico and the US, including daily transactions data and returns data, details on their 10,281 customers, 1,560 products and 24 stores.

<a href="https://www.udemy.com/course/microsoft-power-bi-up-running-with-power-bi-desktop/?couponCode=26BBPAA2MX"> Data Source </a>

The transactional data covers the period from *<ins> 1 January 1997 </ins>* to *<ins> 31 December 1998 </ins>*. The date fields is shifted and extended across fact and dimension tables to align the dataset with the current reporting period and enable realistic relative-date calculations.

## 📊 Report Structure
 * **Executive Summary:** intentionally designed as the entry point into the detailed analysis page. The objective is to answer <ins>what happened</ins> and <ins>where did it happen</ins>
   - *Overview* - provides a high-level overview of business performance in the latest period (year/quarter/month)
   - *Sales Performance* - provides a detailed-level sales performance movement over year/quarter/month
 * **Customers Analytics:** focuses on customer activity, retention and purchasing behaviour. One of the key analytical areas is the relationship between *Reactivated Customers* and *Dormant Customers*. For example, a declining reactivated Customers combined with a increasing dormant customers might suggest that greater difficulty in retaining its existing customer base.
 * **Product Performance:** analyses the performance on each product and brand from both sales and profitability perspectives. The dataset does not provide a formal product category hierarchy. Therefore, product analysis is primarily performed at the brand level, with drill-down to individual product SKUs related to  selected product brands where appropriate
 *  **Store Performance:** focuses on sales and operational perfomance on store-level and type-level. Store types and regions can be further investigated through drill-through analysis.

## ⚠️ Data Assumptions & Limitations
The report and Measures includes several assumptions that should be considered when interpreting the results

 * **Dates -** The <ins>Fact Tables</ins> were originally dated in 1997 and 1998. Dates were shifted forward to create a *2024-2025* analytical period. Dates on <ins>Dimension Tables</ins> were also adjusted where necessary to align them with the analysis period.
 * **Transaction Definition -** The transaction table does not contain a transaction/order ID. Therefore, transaction lines made by the same customer on the same date are assumed to be one transaction for the purpose of transaction-based analysis.
 * **Returns -** The returns table does not contain a transaction/order ID or customer ID. Therefore, each return records cannot be directly linked back to the original customer purchase. Returns are then analysed at the available date, product and store level. In addition, as there are no information for how to deal with each return, all returned products are assumed to be back to inventory and make available for resale. No additional adjustment or analysis is made for damaged, defective, or unsellable returned products. 
 * **Customer Lifecycle -** The available customer data does not provide the information of newly registered customers during the analysis period. Therefore, the analysis focuses on observed customer activity and reactivation rather than attempting to calculate a complete new-customer acquisition funnel.
 * **Product Categories -** The dataset does not provide a formal product category hierachy. Brand is therefore used as the primary product segmentation, with further analysis at product SKU level.
 * **Product Pricing -** The analysis primarily uses the available retail price information. A more complete pricing dataset containing actual transaction prices, promotions and discounts would enable more detailed price-volume-mis and promotion effectiveness analysis.

## 💡 Project Insights
 * **Customers:**
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
