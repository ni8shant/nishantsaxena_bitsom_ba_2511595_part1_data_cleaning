# Part 1: Business Data Cleaning, Validation & Excel Reporting

## Problem Summary

This project focuses on cleaning, validating, and preparing retail order data for business reporting and analysis. The raw dataset contained formatting issues, missing values, duplicate records, invalid discounts, and date inconsistencies.

## Dataset Description

Dataset: Retail Order Transactions

Files:

* raw_orders.xlsx
* cleaned_orders.xlsx

The dataset includes customer, order, shipping, product, sales, cost, and payment information.

## Tools Used

* Microsoft Excel
* Pivot Tables
* Conditional Formatting
* Data Validation
* Excel Functions (TRIM, IF, COUNTIF, YEAR, TEXT, etc.)

## Cleaning Steps Performed

### Text Cleaning

Standardized:

* customer_name
* segment
* region
* state
* city
* category
* sub_category
* ship_mode
* payment_status
* order_status

Actions:

* Removed extra spaces.
* Fixed capitalization.
* Standardized category labels.

### Date Validation

* Standardized order_date and ship_date.
* Created shipping_delay_days.
* Flagged invalid shipping records.

### Missing Values

* Region → Unknown
* Ship Mode → Unknown
* Discount → 0 (where valid)

### Duplicate Handling

* Removed 20 exact duplicate rows.
* Flagged duplicate order IDs for review.

## Business Rules Applied

* Missing region values replaced with Unknown.
* Missing ship_mode values replaced with Unknown.
* Invalid discounts flagged.
* Cancelled orders excluded from completed sales summaries.
* Failed payments excluded from completed sales summaries.
* Refunded orders summarized separately.
* Invalid shipping records flagged.

## Data Quality Summary

* Original Records: 932
* Final Records: 912
* Exact Duplicate Rows Removed: 20
* Duplicate Order ID Records Flagged: 24
* Missing Region Records Filled: 25
* Missing Ship Mode Records Filled: 21
* Invalid Discount Records: 15
* Invalid Shipping Records: 194

## Pivot Reports Created

1. Sales and Profit by Region
2. Sales and Profit by Category and Sub Category
3. Order Count by Ship Mode
4. Profit Margin by Customer Segment
5. Refunded / Cancelled / Failed Orders by Region
6. Monthly Sales Trend

## Key Business Insights

* Certain regions contribute significantly more revenue than others.
* Some customer segments generate stronger profit margins.
* Shipping quality issues exist due to invalid shipping timelines.
* Duplicate order IDs require business review.
* Invalid discounts indicate data-entry control weaknesses.

## Assumptions

* Discounts should fall between 0 and 1.
* Unknown values should not be guessed.
* Duplicate order IDs may represent legitimate transactions.

## Limitations

* No external validation source available.
* Duplicate order IDs require manual investigation.
* Missing values could not always be accurately inferred.

## Screenshots Included

* raw_data_preview.png
* cleaned_data_preview.png
* pivot_summary_1.png
* pivot_summary_2.png
