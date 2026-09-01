# Sales Performance Dashboard

A compact Power BI portfolio project for exploring sales performance across products, categories, regions, and salespeople in France.

![Sales Performance Dashboard](screenshots/dashboard.png)

## Project overview

The report uses a synthetic CSV dataset containing 1,000 orders over approximately 12 months. It covers 20 products, 9 categories, 33 French cities, 11 regions, 12 salespeople, and 5 customer types. Prices and quantities are generated for demonstration purposes and do not represent real transactions.

Power Query imports the UTF-8 CSV, promotes the header row, assigns appropriate data types, and parses unit prices using an English (United States) locale. A calculated `Revenue` column multiplies unit price by quantity.

## Dashboard features

The dashboard includes four headline KPIs:

- Total revenue
- Total orders
- Units sold
- Average order value

Supporting visuals show monthly revenue, revenue by category, revenue by region, and the best-performing products. Slicers allow the report to be filtered by date, category, region, and salesperson.

The core DAX measures are:

```DAX
Total Revenue = SUM(Sales[Revenue])
Total Orders = DISTINCTCOUNT(Sales[OrderID])
Units Sold = SUM(Sales[Quantity])
Average Order Value = DIVIDE([Total Revenue], [Total Orders])
```

## Technologies

- Power BI Desktop
- Power Query
- DAX
- Data visualization

## Repository structure

```text
powerbi-sales-dashboard/
├── data/
│   ├── sales.csv                     # Synthetic source data
│   ├── SalesDashboard.pbip           # Power BI project entry point
│   ├── SalesDashboard.Report/        # Report definition
│   └── SalesDashboard.SemanticModel/ # Data model and DAX definitions
├── screenshots/
│   └── dashboard.png                 # Dashboard preview
├── LICENSE
└── README.md
```

Open `data/SalesDashboard.pbip` in Power BI Desktop to review the report. If the source path differs on your machine, update the CSV connection in Power Query.
