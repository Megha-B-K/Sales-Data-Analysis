# Power BI Sales Data Analysis Dashboard

**Author**: Megha Kallapur  
**Location**: Karnataka, India  
**[GitHub](https://github.com/Megha-B-K)** 
---

## Project Overview

Interactive **Power BI dashboard** analyzing **3,509 sales orders** with comprehensive business intelligence across products, promotions, geography, and time-series trends. Built for revenue optimization and strategic decision-making.

**Dataset**: 50K+ sales records covering Product Name, Promotion Name, City (India-focused), Sales, Profit, Quantity, Discount %

**Business Impact**: Identifies top-performing Apple products, optimal promotions, geographic hotspots, and peak sales periods.

---

## Dashboard Features 

| Visual Type        | Page Name             | Key Insights                            |
|--------------------|-----------------------|-----------------------------------------|
| **Card**           | Total Orders          | 3,509 orders                            |
| **Bar Charts**     | Top/Bottom 5 Products | Apple iPhone/TV dominate sales & profit |
| **Scatter Plot**   | Sales vs Profit       | Strong positive correlation             |
| **Horizontal Bar** | Discount by Promotion | Promotion Name 1: ~28% avg discount     |
| **Line Chart**     | Sales Trends          | 2022-2023 peak periods                  |
| **Map**            | Sales by City         | Karnataka/Maharashtra clusters          |
| **Totals Cards**   | Sales/Profit/Quantity | Multi-metric KPIs                       |

---

## Technical Implementation

### Data Model
Fact Table: Sales (Order ID = Primary Key)
├── Product Name
├── Promotion Name
├── City (Lat/Long for maps)
├── Sales (₹)
├── Profit (₹)
├── Quantity
└── Discount %

Relationships: 1:M on Order ID


### Key DAX Measures
```dax code
-- Profit Margin
Profit Margin = DIVIDE([Total Profit], [Total Sales], 0)

-- Year-over-Year Growth
YoY Sales Growth = 
DIVIDE(
    [Total Sales] - CALCULATE([Total Sales], SAMEPERIODLASTYEAR('Date'[Date])),
    CALCULATE([Total Sales], SAMEPERIODLASTYEAR('Date'[Date]))
)

-- Top N Products
Top N Sales = TOPN(5, 'Sales', [Total Sales], DESC)

-- Average Discount by Promotion
Avg Discount by Promotion = 
AVERAGEX(
    VALUES('Sales'[Promotion Name]),
    CALCULATE(AVERAGE('Sales'[Discount %]))
)

---

### Actionable Business Insights ###
Product Performance: Apple iPhone & Apple TV generate 80%+ of top revenue/profit

Promotion Strategy: Promotion Name 1 delivers highest discount impact (28%)

Profit Correlation: Strong positive Sales-Profit relationship - focus high-volume SKUs

Geographic Focus: Karnataka/Maharashtra cities represent sales hotspots

Seasonal Planning: Sales peak in 2022-2023 - plan inventory accordingly

## Skills Demonstrated:

Power BI Desktop/Service

DAX (Advanced Measures + Calculated Columns)

Data Modeling & Relationships

Geographic Visualization (Maps)

Interactive Dashboard Design
 
**📧 Contact**: meghakallapur@gmail.com  
**📅 Last Updated**: February 2026


Business Intelligence

