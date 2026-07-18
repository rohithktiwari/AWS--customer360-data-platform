# AWS -Customer 360 Data Platform on AWS
![AWS](https://img.shields.io/badge/AWS-232F3E?style=for-the-badge&logo=amazonaws&logoColor=white)
![Amazon S3](https://img.shields.io/badge/Amazon_S3-569A31?style=for-the-badge&logo=amazons3&logoColor=white)
![AWS Glue](https://img.shields.io/badge/AWS_Glue-FF9900?style=for-the-badge)
![Amazon Athena](https://img.shields.io/badge/Amazon_Athena-527FFF?style=for-the-badge)
![SQL](https://img.shields.io/badge/SQL-336791?style=for-the-badge&logo=postgresql&logoColor=white)
![CSV](https://img.shields.io/badge/CSV-F4B400?style=for-the-badge)

An end-to-end data analytics project built on AWS that combines customer information from multiple business systems into a single Customer 360 view using Amazon S3, AWS Glue, and Amazon Athena.

---

## Project Overview

Customer information is usually spread across different business applications. The sales team has purchase history, the support team manages customer issues, marketing tracks campaign responses, and the CRM system stores customer profiles.

Because these systems operate independently, getting a complete view of a customer becomes difficult.

In this project, I used AWS services to centralize these datasets and analyze them using SQL without managing any database servers.

---

## Problem Statement

A company stores customer data across multiple systems:

- CRM
- Transactions
- Support Tickets
- Marketing Campaigns

Since these datasets are isolated, business teams cannot easily answer questions like:

- Who are the highest-value customers?
- Which products generate the most revenue?
- Which customers frequently contact support?
- How effective are marketing campaigns?

---

## Solution

The project stores all datasets in Amazon S3, automatically discovers their schema using AWS Glue, and performs SQL analytics with Amazon Athena.

By joining all datasets together, the project creates a unified Customer 360 view that helps answer business questions from a single place.

---

# Architecture

```
                     🚀 Customer 360 Analytics Platform

                               Source Data

┌────────────────┐ ┌────────────────┐ ┌────────────────┐ ┌────────────────┐
│ 👤 CRM Data     │ │ 💳 Transactions │ │ 🎫 Support     │ │ 📢 Marketing   │
│ Customer Data   │ │ Purchase Data  │ │ Tickets        │ │ Campaigns      │
└────────────────┘ └────────────────┘ └────────────────┘ └────────────────┘
          │                  │                  │                  │
          └──────────────────┴──────────────────┴──────────────────┘
                                     │
                                     ▼
                  ☁️ Amazon S3 (Raw CSV Storage)
                                     │
                                     ▼
                      🔍 AWS Glue Crawler
                                     │
                                     ▼
                     📚 Glue Data Catalog
                                     │
                                     ▼
                     ⚡ Amazon Athena
                                     │
                                     ▼
                     👤 Customer 360 View
                                     │
           ┌─────────────────────────┼────────────────────────┐
           ▼                         ▼                        ▼
 Revenue Analysis          Support Analysis        Marketing Analysis
```

---

# Tech Stack

| Category | Technology |
|----------|------------|
| Cloud | Amazon Web Services (AWS) |
| Storage | Amazon S3 |
| Metadata | AWS Glue Data Catalog |
| Schema Discovery | AWS Glue Crawler |
| Query Engine | Amazon Athena |
| Language | SQL |
| Dataset Format | CSV |

---

# Dataset

The project contains four datasets.

| Dataset | Description |
|----------|-------------|
| CRM | Customer profile information |
| Transactions | Purchase history |
| Support | Customer support tickets |
| Marketing | Campaign interactions |

---

# AWS Services Used

- Amazon S3
- AWS IAM
- AWS Glue Crawler
- AWS Glue Data Catalog
- Amazon Athena

---

# Project Workflow

1. Upload CSV datasets to Amazon S3.
2. Configure IAM permissions.
3. Run AWS Glue Crawler.
4. Automatically create tables in Glue Data Catalog.
5. Query data using Amazon Athena.
6. Join all datasets to build the Customer 360 view.
7. Generate business insights with SQL.

---

# SQL Analysis

The project includes SQL queries for:

- Customer Count
- Revenue Analysis
- Product Performance
- Support Ticket Analysis
- Marketing Campaign Analysis
- Customer 360 View

---

# Business Insights Generated

The platform can answer questions such as:

- Total number of customers
- Total revenue generated
- Revenue by product
- Customers with multiple support tickets
- Marketing campaign performance
- Unified Customer 360 profile

---

# Repository Structure

```
customer360-data-platform-aws
│
├── architecture/
│
├── datasets/
│
├── docs/
│   ├── project-overview.md
│   ├── implementation-notes.md
│   └── business-context.md
│
├── query-results/
│
├── screenshots/
│
├── sql/
│
└── README.md
```

---

# Screenshots



### 1. Amazon S3 Bucket

<img width="1532" height="723" alt="02 amazon s3 bucket" src="https://github.com/user-attachments/assets/42d2fa14-806f-4820-a30c-daa36d172912" />


---

### 2. Folder Structure

<img width="1536" height="716" alt="03 s3 buckets folders created" src="https://github.com/user-attachments/assets/72cfdce1-ac2c-4e53-a8eb-0bb228362e8c" />


---

### 3. Uploaded Datasets

<img width="1536" height="732" alt="04 bucket file uploaded" src="https://github.com/user-attachments/assets/c47c8fba-9754-4a8e-9359-c5345eb66794" />


---


### 4. Athena Query

<img width="1536" height="725" alt="12 Amazo anthena" src="https://github.com/user-attachments/assets/29f01fbf-8029-4c16-b9cf-8796b1f6678c" />



### 5. Glue Crawler Completed

<img width="1532" height="732" alt="11 cralwers creation" src="https://github.com/user-attachments/assets/9e559cc6-94a0-45af-a5ff-1947985da3ac" />


---

# What I Learned

Working on this project gave me practical experience with AWS serverless analytics services. I learned how to store data in Amazon S3, automate schema discovery with AWS Glue, and analyze data directly using Amazon Athena. I also gained a better understanding of how customer data from multiple systems can be combined to create a single analytical view.

---

# Future Improvements

Some possible enhancements include:

- Automated ETL using AWS Glue Jobs
- Data validation pipeline
- Amazon Redshift integration
- Amazon QuickSight dashboards
- Incremental data ingestion
- Data quality monitoring

---

# Author

**Rohit**

Aspiring Data Engineer | SQL | Python | AWS | Azure | Databricks
