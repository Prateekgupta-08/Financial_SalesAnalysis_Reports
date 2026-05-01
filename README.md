# Financial Sales Analysis — Power BI Dashboard

This project is a end-to-end sales analytics dashboard built in Power BI, using Microsoft's Financial Sample dataset. The goal was to transform raw transactional sales data into a clean, interactive report that helps the team quickly understand performance across countries, products, and business segments — without having to dig through spreadsheets.

## Background
The dataset covers sales transactions from **September 2013 to December 2014** across five countries and six products. Before building the dashboards, the raw Excel file went through a full ETL process inside Power Query — cleaning inconsistencies, correcting data types, and structuring the data so visuals would be accurate and performant.

## Dataset
**Source file:** `Financial_Sample.xlsx`

| Detail | Info |
|---|---|
| Total Records | 700 rows |
| Time Period | Sep 2013 – Dec 2014 |
| Countries | Canada, France, Germany, Mexico, United States of America |
| Products | Amarilla, Carretera, Montana, Paseo, Velo, VTT |
| Segments | Government, Small Business, Enterprise, Midmarket, Channel Partners |
| Discount Bands | None, Low, Medium, High |

**Columns in the dataset:**
Segment, Country, Product, Discount Band, Units Sold, Manufacturing Price, Sale Price, Gross Sales, Discounts, Sales, COGS, Profit, Date, Month Number, Month Name, Year

## ETL Process (Power Query)

Before loading data into the model, I ran through the following steps in Power Query:
1. **Loaded the raw Excel file** into Power BI via Power Query Editor
2. **Removed blank and null rows** that were present at the bottom of the sheet
3. **Corrected data types** — marked numeric columns (Sales, Profit, COGS, Units Sold, etc.) as Decimal Number, and Date column as Date type
4. **Cleaned the Discount Band column** — replaced null values with "None" for consistency
5. **Renamed columns** for readability where needed
6. **Verified row count** — confirmed 700 clean records after transformation
7. **Closed and applied** the query to load into the data model

## Dashboard Pages

### Page 1 — Financial Overview
A high-level summary of the business performance across all countries and segments.
- Sales by Country (bar chart) — quick comparison of total sales per country
- Sales by Country (donut chart) — percentage share breakdown
- Gross Sales by Country (pie chart) — gross revenue distribution
- Sum of Sales by Segment (bar chart) — revenue by business segment
- Units Sold by Segment (waterfall chart) — shows increase/decrease/total per segment
- Profit by Country (donut chart) — where the profit is actually coming from

### Page 2 — Country and Product Detail
A more granular view for drilling into specific combinations.
- Sales by Country and Product (clustered bar) — side-by-side product comparison per country
- Gross Sales by Segment and Country (100% stacked bar) — proportional view of each country's contribution within a segment
- Sales by Country (Bing Map) — geographic view of where sales are happening
- KPI Cards — Total Sales, Average Sale, Max Sale at a glance
- Slicers — filter everything by Country, Product, and Segment interactively

## Key Numbers
| Metric | Value |
|---|---|
| Total Sales | $118.73M |
| Total Profit | $16.89M |
| Total Units Sold | 1,125,806 |
| Average Sale per Transaction | $169.61K |
| Highest Single Transaction | $1.16M |

## Key Insights from the Data
- **United States and Canada** are the top two markets by sales volume, each contributing around 21% of total sales.
- **France leads in profitability** with a 22.38% profit share — higher than its sales share, meaning better margins.
- **Mexico consistently underperforms** across sales, gross sales, and profit — worth investigating whether it's a pricing or volume issue.
- **Government is the strongest segment** by both revenue and units sold, suggesting it should remain a priority for the sales team.
- **Channel Partners** move high unit volume but at low sale prices, which is expected given their discount structure.
- **Small Business** generates strong revenue despite lower unit counts, driven by higher sale prices.

## Project Structure
```
financial-sales-analysis/
├── Financial_Sales_Analysis_Report.pbix    # Power BI report file
├── data/
│   └── Financial_Sample.xlsx               # Source dataset
├── screenshots/
│   ├── page1_overview.png
│   └── page2_detail.png
└── README.md
```

## How to Use
1. Clone or download this repository
2. Open `Financial_Sales_Analysis_Report.pbix` in Power BI Desktop
3. If the data source path breaks, go to **Transform Data > Data Source Settings** and point it to your local `data/Financial_Sample.xlsx`
4. Hit **Refresh** and the report will load with all visuals intact
5. Use the slicers on Page 2 to filter by Country, Product, or Segment


## Tools Used
- **Power BI Desktop** — data modeling, ETL, and dashboard development
- **Power Query** — data cleaning and transformation
- **Microsoft Excel** — source data format
- **Bing Maps** — integrated map visual for geographic sales view

## Requirements
- Power BI Desktop (free download from Microsoft)
- Windows OS (Power BI Desktop is Windows-only)
- No additional licenses needed for local use

## Author
Built as part of a data analytics project to demonstrate end-to-end Power BI development — from raw data ingestion and cleaning through to interactive dashboards ready for business use.
