# Online Retail Sales and Customer Behavior Analysis

## Project Background and Overview
This project focuses on an exploratory data analysis of the "Online Retail" dataset, which contains transactional data from a UK-based online retail store between 01/12/2010 and 09/12/2011. The dataset contains information about customer purchases, including product details, quantities, prices, and timestamps.

## Objectives
The main objectives is to conduct an exploratory data analysis to gain insights into the store's
1. Sales trends between 01/12/2010 and 09/12/2011
2. Popular products
3. Customer behavior
4. Analytics insights and data-driven reccomendations

## Data Overview
The dataset is available as a .xlsx file named `Online Retail.xlsx`. The dataset contained 541,909 rows and 8 columns which includes
* __InvoiceNo__: Invoice number of the transaction
* __StockCode__: Unique code of the product
* __Description__: Description of the product
* __Quantity__: Quantity of the product in the transaction
* __InvoiceDate__: Date and time of the transaction
* __UnitPrice__: Unit price of the product
* __CustomerID__: Unique identifier of the customer
* __Country__: Country where the transaction occurred
The initial dataset contained 541,909 rows and 8 columns.

## Data Cleaning
* Missing values were identified in the 'Description' (1454) and 'CustomerID' (135,080) columns.
* Data cleaning steps included:
    * Filling missing 'Description' values by mapping 'StockCode' to existing descriptions and filling any remaining with "Unknown".
    * Dropping rows with missing 'CustomerID' as this is crucial for customer behavior analysis.
    * Dropping 5268 duplicate rows.
    * Removing rows with negative values in 'Quantity' and 'UnitPrice'.
* The final cleaned dataset has 392,732 rows and 8 columns.

## Exploratory Data Analysis (EDA)
* **Quantity and Unit Price Distribution:** Box plots revealed significant outliers in both 'Quantity' and 'UnitPrice' distributions, which were handled by removing negative values.
* **Country Analysis:**
    * There are 38 unique countries in the dataset.
    * The United Kingdom is overwhelmingly the dominant country in terms of transaction count.
    * The top 10 countries by transaction count are United Kingdom, Germany, France, EIRE, Spain, Netherlands, Belgium, Switzerland, Portugal, and Australia.
    * The least 10 countries by transaction count include Malta, United Arab Emirates, European Community, RSA, Lebanon, Lithuania, Brazil, Czech Republic, Bahrain, and Saudi Arabia.
* **Sales Trends:**
    * New columns 'Year', 'Month', 'DayOfWeek', and 'TotalPrice' were created.
    * The monthly sales trend shows a general increase throughout 2011, with a significant peak in November and a drop in December (likely due to the dataset ending early in December).
    * Sales vary across days of the week for each month, with Friday generally showing strong sales.
* **Product Analysis:**
    * **Top 10 Best-Selling Products by Quantity:** PAPER CRAFT , LITTLE BIRDIE, MEDIUM CERAMIC TOP STORAGE JAR, WORLD WAR 2 GLIDERS ASSTD DESIGNS, JUMBO BAG RED RETROSPOT, WHITE HANGING HEART T-LIGHT HOLDER, POPCORN HOLDER, PACK OF 72 RETROSPOT CAKE CASES, ASSORTED COLOUR BIRD ORNAMENT, RABBIT NIGHT LIGHT, and MINI PAINT SET VINTAGE.
    * **Top 10 Products by Total Revenue:** DOTCOM POSTAGE, REGENCY CAKESTAND 3 TIER, PAPER CRAFT , LITTLE BIRDIE, WHITE HANGING HEART T-LIGHT HOLDER, PARTY BUNTING, JUMBO BAG RED RETROSPOT, MEDIUM CERAMIC TOP STORAGE JAR, POSTAGE, Manual, and RABBIT NIGHT LIGHT.
    * There are some differences between the top products by quantity and revenue, indicating that some products with lower quantity sales contribute significantly to revenue due to higher unit prices (e.g., DOTCOM POSTAGE, REGENCY CAKESTAND 3 TIER).
 
## Customer Behavior and Segementation
* **Customer Activity:** Customer activity was summarized by grouping by 'CustomerID' and calculating the total number of unique invoices ('TotalInvoice') and the sum of 'TotalPrice' ('TotalRevenue').
* **RFM Analysis:**
    * Recency, Frequency, and Monetary values were calculated for each customer based on the transaction data, with a snapshot date of one day after the last transaction.
    * Histograms show that Recency is somewhat skewed towards lower values (recent purchases), Frequency is heavily skewed towards lower values (infrequent purchases), and Monetary is also heavily skewed towards lower values (lower spending).
* **K-Means Clustering:**
    * K-Means clustering with 4 clusters was applied to the scaled RFM values to segment customers.
    * The cluster analysis revealed the following customer groups:
        * **Cluster 2 (Top Customer):** Lowest average Recency (7.38 days), highest average Frequency (82.69), and highest average Monetary value (£127,187.96). This group has 13 customers.
        * **Cluster 0 (Loyal Customer):** Low average Recency (15.67 days), high average Frequency (22.05), and high average Monetary value (£12,435.09). This group has 211 customers.
        * **Cluster 3 (Regular Customer):** Moderate average Recency (43.91 days), low average Frequency (3.66), and moderate average Monetary value (£1,344.28). This is the largest group with 3053 customers.
        * **Cluster 1 (Churned Customer):** Highest average Recency (248.56 days), lowest average Frequency (1.55), and lowest average Monetary value (£476.33). This group has 1062 customers.
    * The bar chart visually represents the distribution of customers across these segments, clearly showing that the "Regular Customer" group is the largest, followed by "Churned Customer", "Loyal Customer", and the small but high-value "Top Customer" group.
 
## Key Findings and Reccomendations
* **Key Findings:**
    * The majority of sales come from the United Kingdom.
    * Sales show a strong upward trend throughout the year, peaking in November.
    * There are distinct customer segments based on their purchasing behavior (RFM).
    * A small group of "Top Customers" contribute significantly to revenue.
* **Recommendations:**
    * **Targeting Customer Segments:** Implement tailored marketing strategies for each customer segment. For example, offer loyalty rewards and exclusive access to new products for "Top" and "Loyal" customers, and re-engagement campaigns for "Churned" customers.
    * **Optimizing Inventory and Staffing:** Based on the monthly sales trend, ensure sufficient stock of popular products and adequate staffing levels, especially during peak months like November.
    * **International Expansion:** While the UK is dominant, explore strategies to increase sales in other countries, particularly those in the top 10 by transaction count or revenue.
    * **Product Promotion:** Promote top-selling products by quantity and revenue. Consider bundling items or offering discounts on frequently purchased products.
 
## Conclusion
* This project successfully explored and analyzed the online retail dataset, providing valuable insights into sales trends, popular products, and customer behavior.
* The RFM analysis and K-Means clustering effectively segmented customers into meaningful groups.
* Future work could involve predicting customer churn, performing market basket analysis to understand product associations, or building a recommendation system.
