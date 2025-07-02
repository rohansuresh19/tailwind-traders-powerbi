# 📊 Tailwind Traders Power BI Capstone Project

An interactive Power BI dashboard built to analyze and visualize retail sales, profitability, and tax impact for **Tailwind Traders**, a global retail business. The project demonstrates advanced Power BI skills including data modeling, DAX calculations, performance optimization, and dashboard deployment.

> 🎯 **Goal**: Empower decision-makers with insightful KPIs and trend analysis to drive strategy in a retail context.

## 🧰 Tech Stack
- **Power BI** – Dashboard creation and data visualization  
- **DAX (Data Analysis Expressions)** – Custom KPIs and aggregations  
- **Power Query Editor** – Data shaping and cleaning  
- **Microsoft Excel** – Data sources for sales, purchases, and countries  
- **Python (in Power BI)** – Used to import and structure exchange rate data  

## 🗃️ Data Sources
- `Tailwind-Traders-Sales.xlsx`: Product sales data  
- `Purchases.xlsx`: Purchase and return information  
- `Countries.xlsx`: Country-to-currency mapping  
- **Exchange Data (via Python script)**: Loaded in Power BI using `pandas.read_csv()`  
- `Calendar Table`: Generated in Power BI using DAX  

## 🧮 Key Calculations

| Metric              | Formula / DAX                                                | Description                                |
|---------------------|--------------------------------------------------------------|--------------------------------------------|
| Cost per Unit       | `=E2*0.35`                                                   | 35% of the product price                   |
| Gross Revenue       | `=E2*H2`                                                     | Price × Quantity                           |
| Total Tax           | `=G2*H2`                                                     | Tax × Quantity                             |
| Net Revenue         | `=I2-J2`                                                     | Gross Revenue - Tax                        |
| Profit (DAX)        | `=K2-(F2*G2)`                                                | Net Revenue - Cost                         |
| Yearly Margin       | `DIVIDE(SUM(Profit USD), SUM(Net Revenue USD))`             | Annual profitability ratio                 |
| Quarterly Margin    | `CALCULATE([Yearly Margin], DATESQTD(Calendar[Date]))`      | Profit margin by quarter                   |
| YTD Profit Margin   | `TOTALYTD([Yearly Margin], Calendar[Date])`                 | Year-to-date profit margin                 |
| Median Sales        | `MEDIAN('Sales in USD'[Gross Revenue USD])`                 | Median sales value                         |

## 📊 Report Pages

### Sales Overview
- Visuals: Clustered bar chart, column chart, line graph, pie chart  
- KPIs: Stock Level, Quantity Purchased, Median Sales  
- Filters: Country slicer  
- Theme: "Accessible City Park"

### Profit Overview
- Visuals: Donut chart, area chart, bar graph  
- KPIs: YTD Profit Margin, Net Revenue  
- Filters: Date slicer

## 🧪 Performance Optimization
- Used Power BI **Performance Analyzer**
- Ensured all visuals load in **< 200 milliseconds**

## 📱 Mobile & Dashboard Setup
- **Mobile Layout** configured with top-to-bottom stacking  
- **Dashboard** created on Power BI Service with pinned visuals  
- **Alerts**: Triggered when Gross Revenue USD < $400  
- **Subscriptions**:
  - Sales Summary: Mondays at 5:00 AM  
  - Profit Summary: Mon/Wed/Fri at 6:00 AM  

## ✅ Key Business Questions Answered
- What are the top-performing products and countries?
- How does tax affect profitability?
- Who are the most active sales reps?
- How do sales and profits vary over time?
- How many purchases were returned or not?
- What are the average quantity and price trends?

## 📁 Folder Structure

Tailwind-Traders-Project/
├── Tailwind Traders Report.pbix
├── Tailwind-Traders-Sales.xlsx
├── Purchases.xlsx
├── Countries.xlsx
├── Tailwind_Traders_Capstone_(Proper).docx
└── README.md
