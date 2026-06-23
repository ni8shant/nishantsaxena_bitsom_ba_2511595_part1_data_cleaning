# Cleaning Log

## Issues Identified

The raw dataset contained the following issues:

* Inconsistent text formatting across customer and product fields.
* Missing region values.
* Missing ship mode values.
* Missing discount values.
* Invalid discount values.
* Duplicate records.
* Duplicate order IDs with potential conflicts.
* Invalid shipping records where ship_date occurred before order_date.
* Inconsistent date formats.

## Cleaning Actions Performed

### Text Standardization

Applied TRIM, PROPER, Find & Replace, and manual standardization to:

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

### Date Cleaning

* Standardized order_date and ship_date formats.
* Calculated shipping_delay_days.
* Identified invalid shipping records.

### Missing Values

* Missing region values replaced with "Unknown".
* Missing ship_mode values replaced with "Unknown".
* Missing discount values replaced with 0 where other sales fields were valid.

### Duplicate Handling

* Found 20 exact duplicate rows.
* Removed 20 exact duplicate rows.
* Found 12 duplicate order IDs involving 24 records.
* Duplicate order ID records were retained and flagged for review.

## Business Rules Applied

* Missing region values were filled with "Unknown".
* Missing ship_mode values were filled with "Unknown".
* Invalid discounts were flagged.
* Cancelled orders excluded from completed sales summaries.
* Failed payment records excluded from completed sales summaries.
* Refunded orders summarized separately.
* Invalid shipping records flagged.

## Assumptions

* Discount values should be between 0 and 1.
* Unknown values should remain visible rather than estimated.
* Duplicate order IDs may represent legitimate business scenarios and therefore were not deleted automatically.

## Records Removed

* 20 exact duplicate rows removed.

## Records Flagged

* 24 records flagged for duplicate order review.
* 15 records flagged for invalid discounts.
* 194 records flagged as invalid shipping records.

## Limitations

* No external master data was available to validate customer, region, or product information.
* Unknown values could not be accurately imputed.
* Duplicate order IDs require manual business review.
