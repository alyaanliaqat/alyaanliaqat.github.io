---
title: "University Data Aggregation ETL Pipeline Using Python and AWS"
date: "2025-01-13 00:00:00"
categories: [Python, Automation, API Integration, Deployment, Scheduling, AWS]
tags: [Selenium, BeautifulSoup, Requests, MySQL, mysql-connector-python, ec2-Server, Eventbridge, LambdaFuction]
---
# 🛠️ University Data Aggregation ETL Pipeline

## 📌 Project Overview

This project involves building a fully automated **ETL (Extract, Transform, Load) pipeline** for a client to aggregate data related to U.S. universities from **three different sources**:  
1. **IPEDS (Integrated Postsecondary Education Data System)**
2. **Wikipedia**
3. **UTR (Universal Tennis Rating)**

The main goal was to collect, clean, and store comprehensive university-level information—including facilities, academics, player rankings, and descriptions—into a **MySQL** database and keep the data regularly updated using scheduled cron jobs.

---

## 🚀 Key Features

- 📊 Scrapes 53+ structured data fields per university from IPEDS.
- 🏛️ Collects logos and summaries for universities from Wikipedia.
- 🎾 Gathers player rankings for 1200+ universities using UTR API.
- ☁️ Automatically updates the data monthly using **AWS EventBridge** and **EC2**.
- 🧠 Efficient use of multiple Python libraries and automation techniques.
- 🗃️ Final structured data is stored in a MySQL relational database.

---

## 🔧 Tech Stack & Tools Used

| Category        | Technology                                |
|----------------|--------------------------------------------|
| Language        | Python                                     |
| Web Scraping    | Selenium, BeautifulSoup (bs4), Requests    |
| Database        | MySQL, mysql-connector-python              |
| API Integration | UTR API via Requests                       |
| Automation      | AWS EC2, AWS EventBridge (CRON Scheduler)  |
| Deployment      | Python scripts deployed on AWS EC2         |
| Scheduling      | Monthly refresh using AWS EventBridge cron |

---

## 🧩 Detailed Breakdown

### 1. 📚 IPEDS Web Scraper

- **Objective**: Scrape detailed university data (53+ fields) such as academic offerings, faculty ratios, tuition fees, student demographics, etc.
- **Approach**:  
  - Developed a Python script using `Selenium` to automate the browser and navigate the IPEDS website.
  - Extracted structured data for each university listed.
  - Used `mysql-connector-python` to insert the data into the MySQL database.

---

### 2. 🌐 Wikipedia Data Enrichment

- **Objective**: Enrich the university data with descriptions and logos.
- **Approach**:  
  - Parsed Wikipedia pages using `BeautifulSoup` (`bs4`) to extract the **university description** and **logo URL**.
  - Mapped university names from IPEDS to corresponding Wikipedia pages.
  - Uploaded enriched data into the database using `mysql-connector`.

---

### 3. 🎾 UTR Player Rankings Integration

- **Objective**: Collect and update tennis player rankings for over 1200+ universities.
- **Approach**:  
  - Used `requests` to call UTR’s API endpoints.
  - Extracted and parsed JSON responses containing player names, rankings, and universities.
  - Updated the respective tables in the MySQL database via Python.

---

### 4. ⏲️ Automated Monthly Refresh

- **Deployment**:  
  - All Python scripts were deployed on an **AWS EC2** instance.
- **Scheduler**:  
  - An **AWS EventBridge** rule (CRON) triggers the scripts monthly.
  - Ensures that university data and rankings stay current without manual intervention.

---

## ✅ Outcome

- Collected clean and consistent data from diverse sources.
- Centralized it into a single, queryable MySQL database.
- Reduced manual efforts by automating the entire ETL process.
- Delivered a production-grade solution ready for scaling or feature extension.

---
## 🔚 Conclusion

This project demonstrates a complete end-to-end ETL pipeline that consolidates diverse university-related data from web pages and APIs into a centralized MySQL database. It showcases practical expertise in **Python-based web scraping**, **API integration**, **database operations**, and **cloud automation using AWS**.

The automated monthly refresh using AWS EventBridge ensures that the data remains up-to-date without manual intervention. This makes the solution both scalable and reliable for long-term use.

Overall, this project highlights my ability to manage real-world data engineering tasks and deliver robust, production-ready solutions for clients.
---

## 📬 Contact

**Alyaan Liaqat**  
📧 [alyaanch3@gmail.com] 
🌐 [GitHub Portfolio](https://alyaanliaqat.github.io/)

---