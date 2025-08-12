# Online Retail Sales and Customer Behavior Analysis

## Project Background and Overview
This project focuses on an exploratory data analysis of the "Online Retail" dataset, which contains transactional data from a UK-based online retail store between 01/12/2010 and 09/12/2011. The dataset contains information about customer purchases, including product details, quantities, prices, and timestamps.

## Objectives
The main objectives is to conduct an exploratory data analysis to gain insights into the store's
1. Sales trends between 01/12/2010 and 09/12/2011
2. Popular products
3. Customer behavior
4. Analytics insights and data-driven reccomendations

## Data Overview and Cleaning
The dataset is available as a .xlsx file named `Online Retail.xlsx`. The dataset contains the following columns:
* __InvoiceNo__: Invoice number of the transaction
* __StockCode__: Unique code of the product
* __Description__: Description of the product
* __Quantity__: Quantity of the product in the transaction
* __InvoiceDate__: Date and time of the transaction
* __UnitPrice__: Unit price of the product
* __CustomerID__: Unique identifier of the customer
* __Country__: Country where the transaction occurred

* The initial dataset contained 541,909 rows and 8 columns.
* Missing values were identified in the 'Description' (1454) and 'CustomerID' (135,080) columns.
* Data cleaning steps included:
    * Filling missing 'Description' values by mapping 'StockCode' to existing descriptions and filling any remaining with "Unknown".
    * Dropping rows with missing 'CustomerID' as this is crucial for customer behavior analysis.
    * Dropping 5268 duplicate rows.
    * Removing rows with negative values in 'Quantity' and 'UnitPrice'.
* The final cleaned dataset has 392,732 rows and 8 columns.
