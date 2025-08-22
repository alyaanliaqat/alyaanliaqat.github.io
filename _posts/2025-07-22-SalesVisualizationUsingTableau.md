---
title: "Visualizing Sales Data with Tableau"
date: 2025-07-22
categories: [Portfolio, Tableau]
tags: [Tableau, Data Visualization, Dashboard, Analytics]
description: "A step-by-step walkthrough of building an interactive Tableau dashboard to analyze sales, profit, and product subcategories."
---

# Introduction  

In this blog, I will walk you through the process of creating an **interactive sales dashboard in Tableau**. The dashboard helps uncover insights into sales and profit trends, product subcategories performance, and year-over-year comparisons.  

The purpose of this visualization is to demonstrate how Tableau can be used to transform raw data into actionable insights, empowering businesses to make informed decisions.  

---

# Dataset Overview  

For this project, I used a dataset consisting of four different sheets:  

**1. Orders**  
Columns:  
`Row ID, Order ID, Order Date, Ship Date, Ship Mode, Customer ID, Segment, Postal Code, Product ID, Sales, Quantity, Discount, Profit`  

**2. Product**  
Columns:  
`Product ID, Category, Sub-Category, Product Name`  

**3. Customers**  
Columns:  
`Customer ID, Customer Name`  

**4. Location**  
Columns:  
`Postal Code, City, State, Region, Country/Region`  

This dataset allows us to analyze sales and profit across time, customer segments, and product subcategories while also applying filters for regions and years.  

---

# Steps in Dashboard Creation  

### 1. Sales Comparison Sheet  
The first sheet visualizes **sales comparison between the current year and the previous year** using a line chart.  
- Added **max** and **min points** of sales for the current year, highlighted in **blue (max)** and **orange (min)** for clarity.  

![Sales Line Graph](/assets/images/blog_images/tableauscreenshots/sales.png)
📸 *Sales Line Graph*  

---

### 2. Profit Comparison Sheet  
Next, I created a **profit comparison line chart** to compare profit trends year-over-year.  
- Similar to the sales sheet, the **highest** and **lowest** profit points of the current year were emphasized in **blue and orange**.  

![Profit Line Graph](/assets/images/blog_images/tableauscreenshots/profit.png)
📸 *Profit Line Graph*  

---

### 3. Subcategories Comparison Sheet  
This sheet highlights performance by **product subcategories** such as chairs, phones, tables, etc. It includes:  
- **Bar Chart 1:** Sales value for current vs. previous year.  
- **Bar Chart 2:** Profit value for current vs. previous year.  

![Subcategory Bar Charts](/assets/images/blog_images/tableauscreenshots/subcategories.png)
📸 *Subcategory Bar Charts*  

---

### 4. Sales and Profit Trends Over Weeks  
In this sheet, I visualized weekly sales and profit trends using **step graphs**:  
- **Graph 1:** Weekly Sales  
- **Graph 2:** Weekly Profit  
- A **dotted line** represents the average sales/profit.  
- **Color coding:**  
  - Blue → Above average  
  - Orange → Below average  

![Sales & Profit Weekly Trends](/assets/images/blog_images/tableauscreenshots/weekly.png)
📸 *Sales & Profit Weekly Trends*  

---

### 5. Final Dashboard  
Finally, I combined all the sheets into a single **interactive dashboard**.  
- Added filters allowing users to select the **year** (e.g., 2022, 2023).  
- The dashboard updates dynamically to reflect user selection.  

![Dashboard (2023 Data)](/assets/images/blog_images/tableauscreenshots/2023.png)
📸 *Dashboard (2023 Data)*  

![Dashboard (2022 Data)](/assets/images/blog_images/tableauscreenshots/2022.png)
📸 *Dashboard (2022 Data)*  

---

# Conclusion  

This Tableau dashboard demonstrates how data visualization can uncover key business insights. By breaking down sales and profit performance across time, products, and categories, the dashboard enables decision-makers to:  
- Identify trends and seasonality.  
- Compare performance across years.  
- Understand product subcategories driving growth or loss.  

Through this project, I have showcased my ability to use **Tableau for data analysis and storytelling**, converting raw data into meaningful visual insights.  

---
