# Maven Market Interactive Retail Sales Performance and Commercial Analytics
A Power BI analytics project analysing *sales performance, customer behaviour, product and store performance* for a multi-national grocery retailer with stores across Canada, Mexico and the US.

⛏️**Tools:** Power BI | DAX & Visual Calculation | Power Query | Data Modelling | Time Intelligence | Business Analysis

## ⭐ Project Overview
This project is built on the Maven Market grocery retail dataset, designed to demonstrate how sales, customer, product and store data can be transformed into actionable commercial insights.

The report combines financial and commercial analysis with the objective of moving beyond descriptive reporting to identify the key drivers behind changes in *Sales, Customer behaviour, Products and Stores Performance* and to support *data-driven* decision making. It allows users to move from an executive-level view into detailed store, product and customer analysis through interactive slicers, dynamic measures and drill-through functionality.

## 🎯 Business Objectives
The report was developed to help managers answer 4 key questions:

***1. How is the business performing?***
 * How are sales performing across different time periods, product categories, regions and store channels?
 * How does current performance compare with the prior period (year/quarter/month) and the same period last year?
 * How does sales performance change across YoY, QoQ and MoM periods?
 * How are gross margin and return rate changing?
 * What are the key drivers behind sales growth/decline?
 * Which store channels and product categories contribute the most to overall sales?
 * What is the sales performing expected to be in the next 3 periods?

***2. What drives customer behaviour?***
 * Who are the most valuable and most active customers?
 * How many customers actively making transactions in each quarter/month/week/day?
 * How many customers have returned after being inactive 90+days?
 * What proportion of customers make repeat purchases across different time period?
 * How does Average Order Value and Number of daily transactions change alongside customers during weekday and weekend?
 * Is customer engagement improving or deteriorating?
 * Does each customers group have a specific identifiable product preferences?
 * How much did each customer RFM segment spend, how many orders they placed, and how many customers making purchases during the selected period?

***3. Where are the commercial opportunities and risks?***
 * Which kind of products contribute the most and at the same time move fast?
 * Which kind of products are growing/decling?
 * How many product SKUs is actively selling, compared with the number of products SKUs lost sale, across different time periods?
 * Which products have higher return rates while low sales?
 * Which product SKUs/Categories are frequently purchased together? And which product combinations have the strongest affinity? Understand what drives product sales, prioritise categories with the greatest commercial impact and uncover cross-selling opportunities through category-level purchase associations.
 * What is the root cause on the performance improving or declining across regions, store types, product categories by breaking down the selected measure - Sales Revenue/Sold quantities/Returned quantities

## 🛠️ Key Techniques
The report was built by using the following tools and technologies:
 * 💭 **Power BI Desktop:** Main business intelligence platform used for report creation which includes connecting, modelling, aggregating and visualising data
   - 🔍*Power Query* - Data transformation and cleaning process for extracting, cleaning and shaping data to prepare it for modeling and analysis.
   - 🔗*Data Modeling* - Relationships established among fact tables (transactions and returns) and dimension tables (calendar, customers, products, stores and regions) to enable cross-filtering and accurate calculation.
   - 🗒️*Calculated Column* + *Calculated Table* - extend the data model and create additional analytical dimensions that support business-specific reporting requirements.
   - 🧠*Data Analysis Expressions (DAX)* + *Visual Calculations* - used for creating supporting tables, grouping and aggregating data, dynamic visuals and conditional logic.
   - ⚙️*Parameters* - let users to dynamically update measures inputs to see the impact on a visual or change the metrics/dimensions shown in a visual.
   - 📈*Tooltips* - hiddden custom information to be shown against the hovered product name.
   - 🧐*Report Interactions* - an interactive analytical experience with drill-through, cross-visual interactions, bookmarks and page nagvigation.

 * 🕵️ **Key Analytical Methods:**
   - 🏆*Top/Bottom N Analysis* - identifies highes/lowest performing stores, products or categories.
   - 📅*Time Intelligence* - analyses business growth trends to support performance evaluation and decision-making. It allows users to switch between Year, Quarter and Month on the <ins>Executive Dashboard</ins> page, and between Last 8 Quarters (quarter granular), Last 12 Months (month granular), Last 13 Weeks (week granular) and Last 30 Days (day granular) on the detailed <ins>Customers, Products and Stores</ins> pages.
   - 🎨*RFM Analysis* - segments customers based on their purchasing behaviour/the available 2yrs transaction history, which evaluates **R**ecency (how recently a customer made a purchase), **F**requency (how often a customer made a purchase), **M**onetary (how much did a customer spent in total), and then helps create really effective marketing efforts.
   - ⚖️*Pareto Analysis* - identifies product categories/store types that drive the majority of sales (opportunity) / returns (risks), supporting more targeted resource allocation and performance management, by evaluating cumulative sales contribution to identify the product categories/store types that account for the largest share of revenue.
   - ✨*BCG-Style Matrix* - identifies products that are strong performers, stable revenue contributors, growth opportunities or potential underperformers, by <ins>Growth Rate X Sales Contribution</ins> with a percentile slicer to control the classification boundaries interactively.
   - 🛍️*Basket Analysis* - analyses product affinity and co-purchase behaviour to identify potential cross-selling opportunities and supports sales strategies planning.

## 💾 Data Source
This data is from Maven Market, a multi-national grocery chain with locations in Canada, Mexico and the US, including daily transactions data and returns data, details on their *269,720* Transaction lines, *7,087* Return lines, *10,281* Customers, *1,560* Product SKUs, *24* Stores and *7* Regions.

<a href="https://www.udemy.com/course/microsoft-power-bi-up-running-with-power-bi-desktop/?couponCode=26BBPAA2MX"> Data Source </a>

* **Date Transformation:**
The original data of Transaction and Returns covers the period from *<ins> 1 January 1997 </ins>* to *<ins> 31 December 1998 </ins>*. The date fields is shifted and extended to cover from *<ins> 1 January 2024 </ins>* to *<ins> 31 December 2025 </ins>* across fact and dimension tables to align the dataset with the current reporting period and enable realistic relative-date calculations.

* **Transaction Definition:**
The transaction table does not contain a transaction/order ID. A order ID is created on each transaction line in the format of "*<ins>C</ins>*[5 digits Customer ID]*<ins>S</ins>*[2 digits Store ID]*<ins>D</ins>*[8 digits date in DDMMYYYY]". Therefore, transaction lines made by the same customer at the same store on the same date are assumed to be in the same transaction for the purpose of transaction-based analysis. This transformation process aggregates the <ins>270k</ins> transaction rows into <ins>58,381</ins> order-level rows.

* **Product Categorisation:**
The original product data does not contain product category information. A product hierarchy was therefore created by:
  - Extracting product names from the full product name by removing the product brand
  - Creating a new table via Power Query with 311 distinct product names
  - Manually creating a mapping rule with keywords and the according product subcategory
  - Assigning each product name to its relative subcategory according to the mapping rule
  - Grouping subcategories into main categories

   This transformation process consolidates <ins>1,560</ins> product SKUs into <ins>311</ins> product name after removing product brand, and then into <ins>54</ins> product sub-categories, and into <ins>8</ins> product main categories at the highest level.

## 📊 Report Structure
 * **Executive Summary:** intentionally designed as the entry point into the detailed analysis page. The objective is designed to help decision-makers quickly identify <ins>what happened</ins> and <ins>where did it happen</ins>.
   - *Overview* - provides a high-level overview of business performance in the latest period (year/quarter/month)
   - *Sales Performance* - provides a detailed-level sales performance movement over year/quarter/month

 * **Customers Analytics:** focuses on customer activity, engagement and lifetime value. One of the key analytical areas is to identify inactive, one-off reactivated, successfully reactivated and dormant customers by using a 90-day customer activity framework, and to segment customers based on their *R*ecency, *F*requency, *M*onetary scores. This enables the report to move beyond simple customer counts and investigate customer retention and opportunities for customer growth and re-engagement.

 * **Product Performance:** supports dynamic time-period analysis using selectable time granularities and rolling periods.
   - *Classification* - classifies product categories/brands into ⭐**Star**, 🐄 **Cash Cow**, ❓ **Question Mark** and 🐕 **Dog** which driven by Sales contribution, Growth Rate and user-selected percentile thresholds, with analysing the performance changes across different time periods. This allows users to explore how the product portfolio changes under different assumptions.
   - *Drivers* - identify the key drivers of product performance, pinpoint high-impact main categories and investigate cross-category purchasing relathionships to support sales growth and product strategy
   - *Basket Analysis* - analyses product subcategories/main categories frequently purchased together to identify potential product associations, which can be used to identify potential opportunities for cross-selling, product bundling and promotional planning.

 *  **Store Performance:** evaluates performance across individual stores, regions and store types/channels. This helps identify high-performing locations, underperforming stores and potential operational differences across store types and regions.

## ⚠️ Data Assumptions & Limitations
The report and Measures includes several assumptions that should be considered when interpreting the results

 * **Dates -** The <ins>Fact Tables</ins> were originally dated in 1997 and 1998. Dates were shifted forward to create a *2024-2025* analytical period. Dates on <ins>Dimension Tables</ins> were also adjusted where necessary to align them with the analysis period.

 * **Transactions ID -** Transaction lines made by the same customer at the same store on the same date are assumed to be in the same transaction.

 * **Product Categories -** The dataset does not provide a formal product category hierachy. Product subcategories is created by extracting keywords from each product name and then looking up its corresponding categories on the mapping rule list which the rule can be edited easily on the table of <ins>SubCategories Mapping</ins> and <ins>MainCategories Mapping</ins> on the window of Power Query. But it would be much better and highly recommended to maintain and imported a separate product categories table with category id and the name of sub-category and main category.

 * **Standard Product Price -** the dataset only provides a standard retail price for each product but does not include the actual selling price for each transaction lines. *Sales Revenue* is therefore estimated using the standard retail price (on Products Table) multiplied by the quantity sold (on Transactions data), rather than actual transaction-level revenue. This limitation may affect the accuracy of revenue, gross profit, gross margin, ROI and revenue-based growth analysis (which follows the Quantities Sold movement or remains at the similar level on the report), particularly when discounts, promotions or historical price changes are involved. It may also influence performance assessment on products, channel and stores, BCG classification, RFM segmentation and Pareto analysis.

 * **Price Plausibility -** the standard retail prices are relatively concentrated within a narrow range of $0.50-$3.98, with some prices appearing counterintuitive across product types (e.g. Steady Silky Smooth Hair Conditioner at $1.45 versus Washington Orange Juice at $2.59), even though the original data covers between 1997 and 1998. Although these differences may not neccessarily indicate data errors, the pricing data may not fully reflect realistic market price variations across product categories. Consequently, price-sensitive analyses, including product price comparisons, revenue estimation and price optimisation, should be interpreted with caution. More representative product pricing data and historical transaction-level prices would be required to validate pricing assumptions and support reliable commercial decisions.

 * **No transaction or return data** exists for All <ins>Mexico</ins> and <ins>Canada</ins> regions in 2024. Therefore, trend prediction, YoY growth rate and comparisons for those regions may be distorted and should be interpreted with caution.

 * **Returns -** The returns table does not contain a transaction/order ID or customer ID. Therefore, each return records cannot be directly linked back to the original customer purchase. Returns are then analysed at the available date, product and store level. In addition, as there are no information for how to deal with each return, all returned products are assumed to be back to inventory and make available for resale. No additional adjustment or analysis is made for damaged, defective, or unsellable returned products.

 * **Customer Lifecycle -** The available customer data does not provide the information of newly registered customers during the analysis period. Therefore, the analysis focuses on observed customer activity and reactivation rather than attempting to calculate a complete new-customer acquisition funnel.

 * **RFM segmentation -** is based on the 2-year transaction window ending on the dataset's lastest transaction date. Given the limited observation period and generally low RFM values, a shorter window is not adopted to avoid further limiting the available purchasing history. The static observation window also limits the ability to track changes in customers segments over time. The resulting classifications should therefore be interpreted as a snapshot of observed customer behaviour, rather than a measure of segment migration, long-term loyalty or lifetime customer value.
   
 * **Product BCG classification -** is based on products' sales contribution and growth rate over the entire selected time window.

## 💡 Project Insights
 * **Regions:**
   - Sales trend shows only USA stores (except Central West small grocery store) attended Nov25 Sales Promotion/Boost event (better performance - Higher MoM and YoY growth compared to previous months and year), while Sales in other regions weren't shown an identifiable growth in November 2025.

 * **Customers:**
   - *The customer base* is primarily driven by lower-income, 65+ age group, and consumers with no kids at home; however, their product preferences show no discernible pattern or clear trends
   - *Low income* customers (~55%) contributing more sales than customers in other income groups.
   - Higher proportion of Customers with *Bronze* membership (~56%) brought products between 2024 and 2025.
   - Low-income customers contribute approximately 92% of sales at the Normal membership tier, substantially above the 35%-45% in other membership tiers, highlighting a persistent difference in customer income composition.
   - Approximatly 60% of customers in the system have no childrend at home, while 10% have no childrent recorded. The age profile may partly explain this pattern (32% aged 65+ and 15% aged 45-54), potentially reflecting households whose children have moved out.
   - Canned & Packaged Goods and Vegetables rank among the top 2 product sub-categories by quantity purchased across all analysed customer segments, indicating consistent demand regardless of customer demographics, membership tier or RFM classification, highlighting their importance in product availability and inventory planning.

 * **Products:**
   - Product sub-categories contributing top 6 sales revenue are *Canned & Packet*, *Vegetables*, *Jams & Spreads*, *Fruits*, *Frozen Meals* and *Cheese* throughout 2025, with Biscuits & Crackers briefly replacing Frozen Meals in February. This suggests stable demand across core categories, with limited short-term ranking variation.
   - About 38% of product SKUs were classified as Dogs in 2025, indicating that a substantial portion of the product portfolio had relatively low sales contribution and growth. These products may require further review to assess their commercial relevance and potential for improvement.
   - *Pantry*, *Fridge, Deli & Eggs*, and *Snacks, Treats & Easy Meals* fall within the top 70% cumulative sales contribution under the selected Pareto thresholds, highlighting their importance to overall sales performance.
   - In December 2025, most product categories in South West Gourmet Supermarkets recorded year-over-year sales declines, suggesting that the weakness extended across multiple product categories rather than being isolated to a single category, highlighting a localised performance issue that require further investigation.
   - The 4 highest-volume product subcategories (*Canned & Packet*, *Vegetables*, *Jams & Spreads*, *Fruits*) dominate the confidence rankings, while combinations with higher lift tend to have confidence below 10%. This suggests that frequent co-purchases are concentrated around popular categories, whereas more distinctive associations occur less frequently. This suggests that distinctive cross-category purchasing patterns may be less prevalent in the observed grocery transactions, although further analysis at more transactions and across time windows is needed to validate this finding.

 * **Stores:**
   - *North West* Region (USA) leads in both Sales and Returns, while its return rate remains comparable to other regions at around 1%. Despite its leading sales performance, North West's average order value (AOV) of $29.47 during the last 12 months is only slightly above South West (USA)'s $28.55 and below Mexico's regional AOV which ranged between $29.08 and $37.42.
   - Notably, *Mexico Central* ranks second in Sales despite having fewer customers than North West (1st) and South West (3rd) during the last 12 months, highlighting stronger sales value per order as a potential contributore to its performance.
   - *Supermarket* and *Deluxe Supermarket* is contributing the most sales revenue (80%+) in the analytical period, highlighting these formats as key revenue drivers and potential areas of focus for future business planning.

## 🙌Recommendations
 * **South West** Region experienced a year-over-year decline in customer numbers in majority months of 2025, with 29% of customers classified as Hibernating Customers (Static RFM segmentation as at 31 Dec 2025). Hibernating customers recorded approximately 40% higher average daily order quantities on weekend than on weekdays during June and July 25, while weekend averages were about twice weekday levels during the first week of November. Meanwhile, about 34% of Cheese SKUs sold in November 25 recorded no sales in December 25, highlighting potential customer retention and product continuity concerns that need further investigation.
   - Engage with locat store managers and analyse customer feedback, returns and product-level sales to investigate customer attrition drivers such as service issues, product dissatisfaction or product availability.
   - Review Cheese SKUs with no December sales to identify potential stock availability, demand or product assortment issues.
   - Address identified service or operational issues and reassess product assorment to better align with customer demand.
   - Test targeted weekend re-engagement campaigns if the observed pattern persists to validate weekend engagement opportunities.
   - Track customer retention, sales recovery and return rate to evaluate the effectiveness of the actions.

 * **CDR Grape Jelly** recorded no sales or returns during the analysis period, indicating a potential product availability, listing, or demand issue that needs further investigation.
   - Investigate whether the product is actively stocked and available for sale, to determine whether lacks of transactions reflects limited availability, discontinued status, data issues or weak customer demand, before assessing underlying customer demand.
   - If the product has been discontinued, coordinate with the <ins>IT</ins>/<ins>Data</ins> team to deactivate it in the product master data, for maintaining data integrity and prevent discontinued products from distorting active product and assortment analysis.
   - If the product is available but consistently generates no sales, reassess its relevance to customer demand, promotion plans to accelerate the sale before the expired date, and future sales plans on its pricing, positioning or product assortment.

 * **No transaction & return** data in 2024 was observed for All **Mexico (central, south, east)** regions and **Canada West** region, despite the relevant stores having been opened or remodelled before 2024. This suggests a potential data completeness issue that should be investigated before drawing conclusions about yealy business performance.
   - Escalate the issue to the <ins>IT</ins>/<ins>Data</ins> team to validate the 2024 transaction & return data pipeline

 * Only **Retail Price** is provided for each product SKUs rather than transaction-level selling prices. In addition, some listed prices appear counterintuitive across product types, and their historical accuracy cannot be verified from the available data.
   - Engage with Data/IT team to establish access to transaction-level selling prices, including applicable discounts and promotions
   - Engage Finance, Commercial/Pricing and Data/IT teams to validate product prices against historical pricing records or other reliable reference data, where available, before drawing conclusions from price-based comparisons
   - Re-write the DAX for revenue-related calculations using validated pricing data and reassess revenue-based metrics and product classifications to improve the reliability of commercial insights

 * If analysis on **Periodic RFM segmentation** movement is required:
   - Create a table of monthly customer-level RFM snapshots to monitor segment migration, to identify emerging churn risks and support targeted retention strategies.
   - Pre-calculating RFM metrics in SQL, Data Warehouse can reduce repeated DAX calculations and improve report performance.
