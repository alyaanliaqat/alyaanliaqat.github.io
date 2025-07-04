---
title: "Appointment Management Project on Retool"
date: "2025-05-03 00:00:00"
categories: [Retool, Retool Database, SQL, Javascript]
tags: [Retool, SQL, Resource, Javascript, Automation, End-to-End System]
---
# 🗓️ Appointment Management System – Retool App

This project is a **two-page appointment management system** built using [Retool](https://retool.com), designed to streamline customer flow at service counters such as **document submission** and **collection** desks.

## 🔧 Features

### 1. Token Generator Page
- Users can **generate a token** by entering:
  - Customer Name
  - Purpose of Visit (`Document Submission` or `Document Collection`)
- Each submission:
  - Assigns a **unique token ID**
  - Creates a **PDF token slip**
  - Saves the data into the **Retool Database**
  - Initializes the customer status as `Waiting`

> ![Token Generator Page](/assets/images/blog_images/appointmentmanagement/token_generator.png)  
> *Token Generation Form with PDF Slip Output*

---

### 2. Counter Management Page
- Displays live queues categorized by:
  - **Submission Counter**
  - **Collection Counter**
- Staff can view the **current token and customer name**
- Upon serving a customer:
  - The staff clicks **Next**
  - The current user’s status is updated to `Completed`
  - The **next token** in queue is displayed automatically

> ![Counter Page](/assets/images/blog_images/appointmentmanagement/counter_page.png)  
> *Live Token Queue View with "Next" Functionality*

---

## 🗃️ Tech Stack
- **Retool** (Frontend & Backend UI)
- **Retool Database** (Data storage)
- **PDF Generator** component in Retool
- Conditional logic for real-time queue handling

---

## 🚀 Use Case
This system can be deployed at front desks of:
- Government Offices
- Educational Institutes
- Banks
- Customer Service Centers

It ensures a **transparent**, **organized**, and **digitized queue management** process.

---

## 📬 Contact

**Alyaan Liaqat**  
📧 [alyaanch3@gmail.com]  
🔗 [LinkedIn](www.linkedin.com/in/alyaan-liaqat)  
🌐 [GitHub Portfolio](https://alyaanliaqat.github.io/)

---
