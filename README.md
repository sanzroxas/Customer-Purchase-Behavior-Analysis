# Customer Purchase Behavior Analysis using RFM Segmentation

## Project Overview

This project analyzes customer purchase behavior from the Online Retail II dataset to identify key trends, segment customers using the RFM (Recency, Frequency, MonetaryValue) framework, and provide data-driven recommendations for improving sales and marketing strategies.

## Dataset

The dataset used in this project is the **Online Retail II** dataset from Kaggle.  It contains transactional data from a **UK-based, non-store online retail company specializing in all-occasion giftware**. Many of the company's customers are **wholesalers**.

**Important Note:** The dataset covers transactions occurring between **01/12/2009 and 09/12/2011**.  The analysis and recommendations, particularly regarding December sales figures, must be interpreted in light of this limited date range. The dataset used begins in Dec 2010, so the data is only for one year.

**Source:**

Dr. Daqing Chen, Course Director: MSc Data Science. chend '@' lsbu.ac.uk, School of Engineering, London South Bank University, London SE1 0AA, UK.

[Online Retail Dataset - Kaggle](https://www.kaggle.com/datasets/lakshmi25npathi/online-retail-dataset?resource=download)  _<!-- Replace with the actual link if you have a preferred one -->_

**Attribute Information:**

*   **InvoiceNo:** Invoice number (6-digit integer). A unique identifier for each transaction.  Invoice numbers starting with 'c' indicate cancellations.
*   **StockCode:** Product (item) code (5-digit integer). A unique identifier for each distinct product.
*   **Description:** Product (item) name.
*   **Quantity:** The quantity of each product per transaction.
*   **InvoiceDate:** Invoice date and time.
*   **UnitPrice:** Unit price in sterling (£).
*   **CustomerID:** Customer number (5-digit integer). A unique identifier for each customer.
*   **Country:** Country name.

## Tools and Technologies

*   Python
*   Pandas (data manipulation and analysis)
*   Matplotlib (visualization)
*   Seaborn (visualization)
*   Jupyter Notebook (interactive development and reporting)
*   Squarify (treemap visualization)
*   Numpy (numerical operations)
## Project Structure
    * `customer-purchase-behavior-analysis.ipynb`: The Jupyter Notebook containing the complete analysis, code, visualizations, and explanations.
    * `Online Retail.xlsx`: The raw data file.
    * `requirements.txt`: A list of the Python packages required to run the notebook.

## Data Cleaning and Preparation

The following data cleaning and preparation steps were performed:

*   Rows with missing `Customer ID` values were removed, as customer identification is essential for the analysis.
*   The `InvoiceDate` column was converted to the correct datetime format.
*   The `Customer ID` column was converted to string format.
*   Negative `Quantity` values (representing returns or cancellations) were removed to focus the analysis on purchase behavior.  A separate DataFrame (`returns_df`) was created to analyze returns separately.
*   A `TotalPurchase` column was calculated by multiplying `Quantity` and `UnitPrice`.
* Stock Codes `M` (Manual) and `POST` (Postage) were removed from product-level analyses, as they do not represent standard products.

## Key Findings

1.  **UK Market Dominance:** The overwhelming majority of sales and transactions originate from the United Kingdom, highlighting this market's critical importance.
2.  **Skewed Distributions:** Purchase amounts, purchase frequency, and average purchase value per customer all exhibit highly skewed distributions. Most customers make small, infrequent purchases, while a few customers (including wholesalers) contribute disproportionately to revenue.
3.  **Significant Inactive Segment ("Hibernating"):** A large portion of the customer base is classified as "Hibernating" (low Recency, Frequency, and MonetaryValue), indicating a substantial number of inactive customers.
4.  **Valuable "Champions" Segment:** A smaller segment, "Champions," represents the most valuable customers (high Recency, Frequency, and MonetaryValue).
5.  **Top Products:**
    *   **By Quantity:** "WHITE HANGING HEART T-LIGHT HOLDER" is the top-selling product by quantity. The top sellers are a mix of decorative, gift, and craft items.
    *   **By Revenue:** "WHITE HANGING HEART T-LIGHT HOLDER" and "REGENCY CAKESTAND 3 TIER" are the top revenue generators. Some high-revenue items are not top sellers by quantity, indicating higher price points.
6.  **Incomplete December Data:** The dataset contains data from 01/12/2010 and 09/12/2011, so *December sales and transaction figures are incomplete and do not represent a full month*. This significantly impacts any analysis of monthly trends.

## RFM Segmentation

Customers were segmented using the RFM (Recency, Frequency, MonetaryValue) framework. A simplified 5-segment model was adopted for clarity and actionability:

*   **Hibernating:** Low Recency (haven't purchased in a while).
*   **Active:** Medium Recency (have purchased somewhat recently).
*   **New Customers:** High Recency, but low Frequency.
*   **Promising:** High Recency and Frequency, low MonetaryValue.
*   **Champions:** High Recency, High Frequency, and High MonetaryValue.

The treemap and bar plot visualizations show the distribution of customers across these segments.

## Recommendations

1.  **Prioritize Re-engagement of "Hibernating" Customers (Top Priority):** Implement targeted re-engagement campaigns with special offers, discounts, and personalized product recommendations.
2.  **Maintain Engagement with "Active" Customers:** Continue regular communication, personalized recommendations, and consider a loyalty program.
3.  **Nurture and Retain "Champions":** Provide VIP treatment, exclusive offers, personalized service, and consider a referral program. Recognize that some of these customers may be wholesalers.
4.  **Welcome and Encourage "New Customers":** Send welcome emails with special offers and provide helpful product information.
5.  **Grow the "Promising" Segment:** Offer targeted promotions to encourage more frequent purchases and/or higher spending.
6.  **Focus on the UK Market:** Prioritize marketing, customer service, and localization efforts for the UK.
7.  **Inventory Management for Top Products:** Ensure sufficient stock of top-selling products, especially "WHITE HANGING HEART T-LIGHT HOLDER" and "REGENCY CAKESTAND 3 TIER".
8.  **Explore Product Development:** Consider developing or sourcing products similar to top sellers, focusing on all-occasion giftware.
9.  **Acknowledge Incomplete December Data:** *Clearly state in all analyses and reports that the December sales and transaction figures are based on incomplete data and do not represent a full month.*
10. **Monitor and Refine:** Regularly monitor the performance of each segment and adjust marketing strategies as needed.
11. **Wholesale Customers:** Given that many customers are wholesalers, consider developing specific strategies for this customer segment, such as bulk discounts or dedicated account management.
12. **Analyze Returns:** Further analyze the `returns_df` DataFrame to identify products with high return rates and potential reasons for returns.

## How to Run

1.  Clone this repository: `git clone https://github.com/sanzroxas/Customer-Purchase-Behavior-Analysis`
2.  Install the required packages: `pip install -r requirements.txt`
3.  Open and run the Jupyter Notebook: `jupyter notebook customer-purchase-behavior-analysis.ipynb`

## Author

Cassandra Roxas - [GitHub](https://github.com/sanzroxas) - [LinkedIn](https://www.linkedin.com/in/cassandra-roxas)
