# Retail Store Sales Dataset — Excel Practice Project

A synthetic, deliberately messy retail sales dataset built for practicing real-world Excel skills — from raw, inconsistent data all the way to a dashboard-ready dataset. Unlike pre-cleaned textbook datasets, this one mirrors the kind of inconsistencies found in real business exports: mixed formats, duplicate records, missing values, and inconsistent text entry.

## Contents

| File | Description |
|---|---|
| `Retail_Store_Sales_Data.xlsx` | Main workbook containing two sheets — `Sales Data` (raw, unclean) and `City Region Lookup` (clean reference table) |

## Dataset Summary

- **Theme:** Retail store sales transactions
- **Sales Data sheet:** 11,468 rows × 14 columns
- **City Region Lookup sheet:** 16 rows × 3 columns
- **Format:** Excel Workbook (`.xlsx`)

## Column Reference — Sales Data

| Column | Description |
|---|---|
| Order ID | Unique order identifier |
| Order Date | Order date, stored as text in three different formats |
| Customer Name | Customer full name — inconsistent capitalisation and spacing |
| City | Customer city — includes alternate/legacy city names |
| Product Category | Product category — includes label variants |
| Product Name | Specific product ordered |
| Quantity | Units ordered — includes blanks, placeholder text, and invalid values |
| Unit Price | Price per unit — mixed numeric and text (currency symbols, comma separators) |
| Discount (%) | Discount applied — includes blanks and an outlier value |
| Payment Mode | Payment method used — includes app-specific labels for UPI |
| Store Branch | Fulfilling store branch |
| Customer Rating | Post-purchase rating, 1–5 — includes blanks |
| Customer Phone | Contact number — five different formatting styles |
| Returned | Return status — inconsistent boolean representations |

## Column Reference — City Region Lookup

| Column | Description |
|---|---|
| City | City name (canonical spelling) |
| Region | Geographic region (North / South / East / West) |
| State | State name |

## Intentional Data Quality Issues

The dataset was engineered with the following real-world data problems, for cleaning practice:

- Mixed date formats stored as text (`DD-MM-YYYY`, `YYYY/MM/DD`, `DD Mon YYYY`)
- Numbers stored as text (currency symbols, comma separators, padding spaces)
- Inconsistent capitalisation and stray whitespace across text fields
- Alternate/legacy place names (e.g. Bombay/Mumbai, Madras/Chennai, Calcutta/Kolkata)
- Category label drift (e.g. "Electronics" vs "Electronic Items")
- True blanks mixed with placeholder "missing" values (`N/A`, `NA`, `-`, `null`)
- Invalid values (zero/negative quantities, zero or extreme prices, discounts over 100%)
- 300 exact duplicate rows and 150 near-duplicate rows (same order, re-entered with different formatting)
- 18 fully blank rows
- Inconsistent boolean representations (`Yes` / `Y` / `1` / `TRUE` vs `No` / `N` / `0` / `FALSE`)

## Skills Practiced

- **Data cleaning:** TRIM, PROPER/UPPER/LOWER, VALUE, SUBSTITUTE, Find & Replace, Remove Duplicates
- **Date functions:** DATEVALUE, MONTH, YEAR, WEEKDAY, EDATE, DATEDIF
- **Text functions:** LEFT, RIGHT, MID, CONCATENATE/TEXTJOIN, FIND
- **Aggregation:** SUM, SUMIF, SUMIFS, COUNTIF, COUNTIFS, AVERAGEIFS
- **Lookups:** VLOOKUP / INDEX-MATCH against the City Region Lookup sheet
- **Conditional logic:** IF, IFS, nested IF
- **Analysis & visualization:** PivotTables, PivotCharts, slicers, dashboard design

## Suggested Workflow

1. **Clean** — standardise text casing/spacing, parse the date formats, convert prices to numbers, resolve duplicates and missing values
2. **Enrich** — pull in Region via VLOOKUP, calculate Revenue (`Quantity × Unit Price × (1 − Discount)`)
3. **Analyze** — PivotTables for category, region, and branch breakdowns
4. **Visualize** — build a dashboard with KPI cards, trend charts, and slicers

## Notes

This is a synthetic dataset generated for learning and practice purposes. It does not represent any real company, transaction, or individual.
