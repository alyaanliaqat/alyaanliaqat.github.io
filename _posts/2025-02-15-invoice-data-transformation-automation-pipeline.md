---
title: "Invoice Data Transformation & Automation Pipeline"
date: "2025-02-15 00:00:00"
categories: [Python, Automation, Deployment, Scheduling, AWS]
tags: [pandas, MySQL, mysql-connector-python, ec2-Server, Eventbridge, LambdaFuction]
---
# 🧾 Invoice Data Transformation & Automation Pipeline

## 📌 Project Overview

This project involved building a **data transformation pipeline** for a client to process and restructure invoice-level data stored in a MySQL database. The original dataset contained over **140,000 invoices**, each with **23 fields**, tied to various categories such as `purchase`, `bonus`, `transfer`, and `promo`. The goal was to consolidate this raw data into a more meaningful format by **grouping, aggregating, and reassigning** invoice categories based on specific business logic.

---

## 🚀 Key Features

- 🔁 Grouped invoices by `company_id` to compute aggregate metrics.
- ➕➖ Subtracted negative amount categories (e.g., bonus/promo) from positive categories (e.g., purchase/transfer).
- 🔄 Reassigned the category of each negative invoice to match the category from which it was offset.
- ⚡ Utilized Python's **multiprocessing** for performance optimization on large datasets.
- 📦 Uploaded final transformed records to a new MySQL table using `mysql-connector`.
- ☁️ Deployed the script to **AWS EC2** and automated daily updates.

---

## 🔧 Tech Stack & Tools Used

| Category        | Technology                                |
|----------------|--------------------------------------------|
| Language        | Python                                     |
| Data Handling   | pandas                                     |
| Parallelism     | multiprocessing                            |
| Database        | MySQL, mysql-connector-python              |
| Deployment      | AWS EC2                                    |
| Automation      | Daily cron job on EC2                      |

---

## 🧩 Detailed Breakdown

### 1. 📊 Data Source & Goal

- **Source**: MySQL database containing raw invoice data with over 140k entries.
- **Objective**: Transform invoice data into a structured summary table grouped by `company_id`, aligning business categories and computing final balances.

---

### 2. 🔄 Transformation Logic

- **Grouping**: Grouped invoices by `company_id`.
- **Categorization**: Within each group, invoices were classified into positive (e.g., `purchase`, `transfer`) and negative categories (e.g., `bonus`, `promo`).
- **Calculation**: For each company:
  - Subtracted the **total negative amounts** from corresponding **positive category totals**.
  - **Reassigned** the negative invoice rows to the positive category they offset.

---

### 3. 🧠 Implementation

- **Data Processing**:
  - Handled large data using **pandas** for efficient manipulation.
  - Applied **Python's multiprocessing module** to process invoice groups in parallel, significantly improving performance.
- **Database Update**:
  - Used `mysql-connector-python` to write the transformed data to a **new destination table** in the client’s database.

---

### 4. ☁️ Deployment & Automation

- **Deployment**:
  - The Python script was deployed on an **AWS EC2** instance.
- **Automation**:
  - Set up a **daily cron job** on the EC2 instance to ensure the new table remains updated with the latest transformations.

---

## ✅ Outcome

- Transformed and optimized a high-volume invoice dataset.
- Delivered a client-ready solution capable of running daily with minimal intervention.
- Ensured data accuracy through rigorous testing and debugging.
- Improved runtime performance using parallel data processing.

---

## 🔚 Conclusion

This project is a strong example of applying **data engineering practices** to real-world financial data. It involved building a complex but efficient ETL process with **custom business logic**, handling large-scale data using **parallelism**, and deploying it as a **cloud-based automated solution**. The pipeline now operates daily, providing up-to-date structured insights to the client from raw invoice-level data.

---
## 📬 Contact

**Alyaan Liaqat**  
📧 [alyaanch3@gmail.com] 
🌐 [GitHub Portfolio](https://alyaanliaqat.github.io/)

---