# 🛒 E-Commerce Sales Analysis – Power BI

A beginner-friendly **E-Commerce Sales Analysis project built using Microsoft Power BI** to analyze sales performance, profitability, products, categories, regions, and sales channels.

The project demonstrates practical Power BI skills including **Power Query, data modeling, DAX measures, KPI reporting, interactive dashboards, and business analysis**.

---

## 📌 Navigation

* [📊 Dashboard](#-dashboard)
* [🎯 Objective](#-objective)
* [📂 Dataset](#-dataset)
* [🛠️ Power BI Workflow](#-power-bi-workflow)
* [📐 DAX Measures](#-dax-measures)
* [📅 Date Table](#-date-table)
* [📊 Dashboard Visuals](#-dashboard-visuals)
* [🎛️ Dashboard Filters](#-dashboard-filters)
* [📁 Repository Structure](#-repository-structure)
* [🧠 Skills Demonstrated](#-skills-demonstrated)
* [💡 Business Questions](#-business-questions)
* [🚀 How to Use](#-how-to-use)
* [📌 Project Outcome](#-project-outcome)
* [⚠️ Dataset Note](#-dataset-note)

---

## 📊 Dashboard

The Power BI dashboard provides an interactive overview of e-commerce business performance.

### Key Performance Indicators

The dashboard can include KPI cards for:

* 💰 Total Sales
* 📈 Total Profit
* 📦 Total Quantity Sold
* 🛍️ Total Orders
* 💵 Average Order Value
* 📊 Profit Margin

### Main Analysis Areas

The dashboard analyzes:

* Sales performance
* Profitability
* Product performance
* Category performance
* Regional performance
* Sales channel performance
* Monthly sales trends

---

## 🎯 Objective

The primary objective of this project is to analyze e-commerce sales data and generate meaningful business insights using Power BI.

The analysis focuses on:

1. Understanding overall sales performance.
2. Measuring total profit and profitability.
3. Identifying top-performing products.
4. Comparing product categories.
5. Analyzing sales across different regions.
6. Comparing sales channels.
7. Identifying monthly sales trends.
8. Creating an interactive business dashboard.

---

## 📂 Dataset

The project uses:

```text
ecommerce_sales_data.csv
```

The dataset contains **500 sample transactions for 2025**.

### Dataset Characteristics

* 📅 Year: 2025
* 📦 Transactions: 500 sample records
* 🛍️ E-Commerce sales data
* 🌎 Multiple regions
* 🏷️ Multiple categories
* 🛒 Multiple sales channels
* 📦 Product-level information
* 💰 Sales and profit information

The dataset is used for educational and portfolio demonstration purposes.

---

## 🛠️ Power BI Workflow

The project follows the following Power BI workflow:

```text
CSV Dataset
     ↓
Power Query
     ↓
Data Cleaning & Transformation
     ↓
Data Model
     ↓
Date Table
     ↓
DAX Measures
     ↓
Dashboard Visuals
     ↓
Slicers & Filters
     ↓
Interactive Power BI Dashboard
```

---

## 🔄 Step 1 – Import the Dataset

Open **Power BI Desktop**.

Navigate to:

```text
Home → Get Data → Text/CSV
```

Select:

```text
ecommerce_sales_data.csv
```

Then load the dataset into Power BI.

---

## 🧹 Step 2 – Data Preparation

Use **Power Query** to prepare the dataset before creating the dashboard.

Typical preparation steps include:

* Checking column data types
* Formatting date columns
* Checking for missing values
* Removing duplicate records if required
* Renaming columns where necessary
* Ensuring numerical columns use the correct data type
* Preparing categorical fields for analysis

---

## 📐 DAX Measures

Create the required DAX measures using the formulas provided in:

```text
DAX_Measures.txt
```

Typical measures used in the dashboard may include:

```DAX
Total Sales = SUM(Sales[Sales])

Total Profit = SUM(Sales[Profit])

Total Quantity = SUM(Sales[Quantity])

Total Orders = DISTINCTCOUNT(Sales[Order_ID])

Average Order Value = DIVIDE([Total Sales], [Total Orders])

Profit Margin = DIVIDE([Total Profit], [Total Sales])
```

> Update table and column names if they differ from the actual dataset.

---

## 📅 Date Table

Create a dedicated Date Table to support time-based analysis.

Example:

```DAX
DateTable =
CALENDAR(
    DATE(2025,1,1),
    DATE(2025,12,31)
)
```

Additional columns can be created for:

* Year
* Month
* Month Number
* Quarter
* Month-Year

Example:

```DAX
Year = YEAR(DateTable[Date])

Month = FORMAT(DateTable[Date], "MMMM")

Month Number = MONTH(DateTable[Date])

Quarter = "Q" & FORMAT(DateTable[Date], "Q")

Month Year = FORMAT(DateTable[Date], "MMM YYYY")
```

After creating the Date Table:

```text
Model View
     ↓
Select DateTable
     ↓
Table tools
     ↓
Mark as date table
     ↓
Select Date column
```

Create a relationship between the Date Table and the sales transaction date column.

---

## 📊 Dashboard Visuals

The dashboard can contain the following visuals.

### 1. KPI Cards

Use Card visuals to display:

* Total Sales
* Total Profit
* Total Orders
* Total Quantity
* Average Order Value

---

### 2. Monthly Sales Trend

**Visual:** Line Chart

**Axis:**

```text
Month Year
```

**Values:**

```text
Total Sales
```

This visual helps identify monthly sales patterns and changes over time.

---

### 3. Sales by Category

**Visual:** Clustered Column Chart

**Axis:**

```text
Category
```

**Values:**

```text
Total Sales
```

This helps identify the strongest-performing categories.

---

### 4. Profit by Category

**Visual:** Bar Chart

**Axis:**

```text
Category
```

**Values:**

```text
Total Profit
```

This compares profitability across product categories.

---

### 5. Sales by Region

**Visual:** Bar Chart / Map

**Axis or Location:**

```text
Region
```

**Values:**

```text
Total Sales
```

This shows which regions contribute the most to overall sales.

---

### 6. Sales by Channel

**Visual:** Donut Chart

**Legend:**

```text
Channel
```

**Values:**

```text
Total Sales
```

This compares different e-commerce sales channels.

---

### 7. Top Products

**Visual:** Bar Chart

**Axis:**

```text
Product
```

**Values:**

```text
Total Sales
```

Apply a Top N filter to identify the highest-performing products.

---

### 8. Sales vs Profit

**Visual:** Combo Chart

Use:

```text
Sales
Profit
```

This provides a comparison between revenue generation and profitability.

---

## 🎛️ Dashboard Filters

Add slicers to make the dashboard interactive.

Recommended slicers:

* 📅 Year
* 🌎 Region
* 🏷️ Category
* 🛒 Channel

Users can select different values to dynamically update the dashboard visuals.

---

## 🧠 Business Questions

The dashboard is designed to answer questions such as:

### Sales

* What is the total sales value?
* How are sales changing month by month?
* Which regions generate the most sales?
* Which channels contribute the most revenue?

### Profitability

* What is the total profit?
* Which categories generate the highest profit?
* Which products are most profitable?
* Which regions have stronger profitability?

### Products

* Which products generate the highest sales?
* Which products have the strongest performance?
* Which categories contain the best-performing products?

### Channels

* Which sales channel generates the most revenue?
* How does profitability differ across channels?

---

## 📁 Repository Structure

```text
E-Commerce-Sales-Analysis-PowerBI/
│
├── 📄 ecommerce_sales_data.csv
├── 📄 DAX_Measures.txt
├── 📖 README.md
└── 📊 ECommerce_Sales_Dashboard.pbix
```

### File Description

| File                             | Description                        |
| -------------------------------- | ---------------------------------- |
| `ecommerce_sales_data.csv`       | 500 sample e-commerce transactions |
| `DAX_Measures.txt`               | DAX measures used for the analysis |
| `README.md`                      | Project documentation              |
| `ECommerce_Sales_Dashboard.pbix` | Final Power BI dashboard           |

> The `.pbix` file should be added to the repository after completing the dashboard in Power BI Desktop.

---

## 🧰 Technologies Used

| Technology             | Purpose                                   |
| ---------------------- | ----------------------------------------- |
| **Microsoft Power BI** | Dashboard and data visualization          |
| **Power Query**        | Data cleaning and transformation          |
| **DAX**                | Measures and calculations                 |
| **CSV**                | Source dataset                            |
| **GitHub**             | Project documentation and version control |

---

## 🧠 Skills Demonstrated

This project demonstrates the following data analytics skills:

* Power BI
* Power Query
* Data Cleaning
* Data Transformation
* Data Modeling
* DAX
* Calculated Measures
* Date Table Creation
* KPI Development
* Data Visualization
* Interactive Dashboard Design
* Business Analysis
* Sales Analysis
* Profitability Analysis
* Regional Analysis
* Product Analysis
* Channel Analysis
* Time-Series Analysis

---

## 🚀 How to Use

### 1. Clone or Download the Repository

Download the project files from this GitHub repository.

### 2. Open Power BI Desktop

Install and open **Microsoft Power BI Desktop**.

### 3. Import the Dataset

Go to:

```text
Home → Get Data → Text/CSV
```

Select:

```text
ecommerce_sales_data.csv
```

### 4. Prepare the Data

Use Power Query to verify:

* Data types
* Dates
* Numeric fields
* Missing values
* Duplicate records

### 5. Create DAX Measures

Open:

```text
DAX_Measures.txt
```

Copy the required measures into Power BI.

### 6. Create the Date Table

Create the Date Table and establish the appropriate relationship with the sales data.

### 7. Build the Dashboard

Create the recommended:

* KPI Cards
* Line Charts
* Bar Charts
* Column Charts
* Donut Charts
* Combo Charts
* Slicers

### 8. Save the Power BI File

Save the completed dashboard as:

```text
ECommerce_Sales_Dashboard.pbix
```

---

## 📌 Project Outcome

The final Power BI dashboard provides an interactive view of e-commerce performance and enables users to analyze:

```text
Sales
  ↓
Profit
  ↓
Products
  ↓
Categories
  ↓
Regions
  ↓
Channels
  ↓
Monthly Trends
```

The dashboard transforms transaction-level sales data into an easy-to-understand business reporting solution.

---

## 📈 Expected Analysis Flow

```text
500 Transactions
       │
       ▼
Data Cleaning
       │
       ▼
Power Query
       │
       ▼
Data Model
       │
       ▼
DAX Measures
       │
       ▼
KPI Analysis
       │
       ▼
Sales / Profit / Product / Region / Channel Analysis
       │
       ▼
Interactive Dashboard
```

---

## ⚠️ Dataset Note

The dataset contains **500 sample transactions for 2025** and is intended for **educational, learning, and portfolio demonstration purposes**.

The data does not represent actual company or customer transactions.

---

## 🎓 Learning Outcomes

By completing this project, you can demonstrate your ability to:

* Import data into Power BI
* Clean and transform data using Power Query
* Build a basic data model
* Create and use a Date Table
* Write DAX measures
* Build KPI cards
* Design interactive visualizations
* Add slicers and filters
* Analyze sales and profitability
* Build a professional Power BI dashboard
* Present business insights through data visualization

---

## ⭐ Project Summary

| Category          | Details                                                 |
| ----------------- | ------------------------------------------------------- |
| **Project**       | E-Commerce Sales Analysis                               |
| **Tool**          | Microsoft Power BI                                      |
| **Dataset**       | 500 Sample Transactions                                 |
| **Year**          | 2025                                                    |
| **Data Format**   | CSV                                                     |
| **Analysis**      | Sales, Profit, Products, Categories, Regions & Channels |
| **Visualization** | Interactive Power BI Dashboard                          |
| **Techniques**    | Power Query, Data Modeling & DAX                        |
| **Output**        | `.pbix` Power BI Dashboard                              |

---
