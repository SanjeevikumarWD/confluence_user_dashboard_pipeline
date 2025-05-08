# 📊 Confluence User Engagement Dashboard Pipeline

## 📝 Overview

This project implements an **ETL pipeline** to analyze user engagement in Atlassian’s **Confluence**, a collaboration platform. It processes **mock Confluence user activity data** (e.g., page creations, edits, comments) to generate a dashboard of engagement metrics, such as:

- Top contributors  
- Action trends  
- Popular pages

The pipeline showcases skills in **Python (Pandas)**, **SQL (PostgreSQL)**, **data modeling**, and optional **PySpark** for big data processing — aligning with data engineering tasks for Atlassian products.

---

## 🚀 Features

- **Extract**: Reads mock Confluence activity data from a JSON structure.
- **Transform**: Cleans and enriches data using Pandas (deduplication, engagement categorization).
- **Load**: Stores data in a PostgreSQL database with a relational schema (`activities`, `users` tables).
- **Analyze**: Runs SQL queries to derive engagement metrics.
- **Error Handling**: Includes robust `try-except` blocks for database operations.
- **Optional PySpark**: Aggregates data for scalability.

---

## 📈 Metrics Generated

### ✅ Top Users by Action Count
Ranks users by the number of actions (e.g., page creations, edits, comments).

> Example:  
> `User 101: 2 actions`  
> `User 102: 2 actions`

### 📊 Action Trends
Shows the frequency of action types (e.g., `page_create`, `comment`) over time to highlight collaboration patterns.

> Example:  
> `page_create: 2`  
> `comment: 2`  
> `page_edit: 1`

### 📌 Top Pages by Actions
Identifies pages with the most actions (e.g., edits, comments) to find popular content.

> Example:  
> `Page 1: 2 actions`  
> `Page 2: 2 actions`

---

## 🗃️ Schema

### 🔹 Table: `activities`
| Column            | Type        | Description                         |
|-------------------|-------------|-------------------------------------|
| `user_id`         | `INT`       | ID of the user                      |
| `action`          | `VARCHAR`   | Type of action (create/edit/comment)|
| `timestamp`       | `TIMESTAMP` | Time of action                      |
| `page_id`         | `INT`       | Associated page                     |
| `engagement_level`| `VARCHAR`   | Categorized engagement level        |

### 🔹 Table: `users`
| Column           | Type       | Description                          |
|------------------|------------|--------------------------------------|
| `user_id`        | `INT`      | Primary Key                          |
| `action_count`   | `INT`      | Total actions by user                |
| `top_engagement` | `VARCHAR`  | Most frequent engagement level       |

---

## 🛠️ Prerequisites

- **Python 3.8+**
- **PostgreSQL** (e.g., `confluence_db`)
- **Python Libraries**:
  - `pandas`
  - `psycopg2`
  - `pyspark` *(optional)*
- **Java** *(only if using PySpark)*

---

## ⚙️ Setup Instructions

### 1. 📥 Clone the Repository
```bash
git clone https://github.com/your-username/confluence-user-engagement-pipeline.git
cd confluence-user-engagement-pipeline
