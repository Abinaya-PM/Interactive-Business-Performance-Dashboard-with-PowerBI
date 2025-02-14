# Interactive Business Performance Dashboard with Power BI  

## Overview  
This project involves designing and developing an interactive Power BI dashboard to analyze business performance using the Adventure Works dataset. The dashboard delivers key insights into revenue, profit, orders, return rates, product trends, customer behavior, and geographical sales distribution, helping businesses make data-driven decisions.  

## Key Features  
- **Data Transformation (ETL):** Cleaned and structured raw data using Power Query.  
- **Data Modeling (DAX):** Built calculated measures for revenue, profit, orders, and trends.  
- **AI-Driven Analytics:** Integrated Smart Narratives for automated insights and Anomaly Detection for identifying unusual trends.  
- **Dynamic Filtering & Drill-Through:** Users can interact with slicers, buttons, and drill-through actions to explore data at different levels.  
- **Multiple Selection Options:** Allows users to switch between key metrics like Orders, Revenue, Profit, and Returns dynamically.  

## Dataset  
The AdventureWorks database is a sample dataset from Microsoft, designed for business analytics. It contains sales transactions, product data, customer demographics, and geographical details.  

### Data Tables  
- **Lookup Tables (Dimensions):** Customer, Product, Product Category, Product Sub-Category, Territory, Calendar.  
- **Fact Tables:** Sales Data, Returns Data.  
- **ETL Process:** Data cleaning and transformation were performed using Power Query.  

### Data Model (Relationships)  
- Primary Keys (PK) in Lookup Tables connected to Foreign Keys (FK) in Fact Tables.  
- Examples:  
  - `Customer Lookup[Customer Key]` → `Sales Data[Customer Key]`  
  - `Product Lookup[Product Key]` → `Sales Data[Product Key]` → `Returns Data[Product Key]`  
  - `Territory Lookup[Sales Territory Key]` → `Sales Data[Territory Key]`  
  - `Calendar Lookup[Date]` → `Sales Data[Order Date]`  

## Dashboards & Visualizations  

### Dashboard 1: Executive Dashboard  
Provides a high-level overview of business performance, including total revenue, profit, orders, and return rate. Includes trend analysis, category-wise performance, and top 10 products. Features interactive filtering, dynamic text cards, and cross-dashboard navigation.  

### Dashboard 2: Geographical Analysis  
Visualizes sales distribution across regions using an interactive map. Includes buttons for selecting specific continents.  

### Dashboard 3: Product Details  
Allows detailed product performance analysis, with monthly target comparisons (Orders, Revenue, Profit) and a price adjustment analysis. Includes a metric selector for dynamic insights and trend analysis.  

### Dashboard 4: Customer Insights  
Analyzes customer behavior, segmentation, and purchasing trends. Includes KPIs for Total Customers & Revenue per Customer, along with top customer highlights and AI-powered insights (Smart Narratives).  

### Dashboard 5: Growth Rate Analysis  
Tracks Year-over-Year (YoY) revenue growth trends, including total revenue, previous year comparisons, and average YoY growth rate (22%).  

## Tools & Technologies  
- **Business Intelligence Tool:** Power BI Desktop  
- **Data Processing:** Power Query  
- **Data Modeling & Calculations:** DAX (Data Analysis Expressions)  
- **Visualization Types:** Line charts, bar charts, pie charts, tables, maps, donut charts, KPI cards, Smart Narratives, Anomaly Detection  

## Key Insights & Learnings  
- **22% YoY Revenue Growth (2020-2022).**  
- **Product Performance Analysis:** Identified top-performing & underperforming products.  
- **Customer Behavior Analysis:** Segmentation by income, occupation, and spending patterns.  
- **Geographical Trends:** Sales performance across different continents and countries.  
- **AI-Driven Insights:** Smart Narratives for automated business analysis.  
- **Dynamic Metrics & Filtering:** Users can toggle between different performance metrics.  

## Future Enhancements  
- **Predictive Analytics:** Implement revenue and demand forecasting.  
- **Advanced Visuals:** Use Treemaps and Waterfall Charts for deeper insights.  
- **Real-Time Data Integration:** Connect to live data sources for real-time tracking.  
