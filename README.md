# 🔐 Cyber Security Project: Splunk Ignite  
### Project Title: Log Analysis & Threat Detection Using Splunk: Data Ingestion to Dashboarding  

---

## 📖 Project Description
This project demonstrates how to ingest, analyze, and visualize log data using **Splunk’s Search & Reporting** capabilities.  
We focus on **login event data** (success/failure) to detect suspicious authentication patterns.  

The objective is to:
- Gain hands-on experience with Splunk log ingestion.
- Learn SPL (Search Processing Language) queries for event analysis.
- Create dashboards for cybersecurity monitoring.  

---

## 📌 What is this Project About?
- Understand how to ingest and structure log data within Splunk.  
- Learn to write SPL queries to analyze login events.  
- Develop interactive dashboards to visualize authentication trends.  
- Detect anomalies and suspicious login behavior.  

---

## ⚙️ Steps Performed

### 1. Prepare the Dataset
A **sample structured log file** (`sample.csv`) was created with the following fields:
- `timestamp`  
- `username`  
- `ip_address`  
- `status` (success/failure)  

👉 [View Dataset](./dataset/sample.csv)

---

### 2. Upload the Data to Splunk
- Open **Splunk Search & Reporting app**.  
- Go to `Settings → Add Data → Upload`.  
- Upload `sample.csv`.  
- Choose **Source Type: csv**.  
- Assign to index → `bootcamp_logs`.  

---

### 3. Run SPL Queries
We executed SPL queries to analyze login patterns.  
All queries are documented in [`spl_queries.txt`](./queries/spl_queries.txt).  

**Examples:**

## 1. Count login successes and failures:
```
index=bootcamp_logs | stats count by status
```
✔ Shows how many successful vs failed logins occurred. 

## 2. Identify suspicious usernames:
```
index=bootcamp_logs status=failure | stats count by username
```

✔ Detects accounts with high failed attempts.

## 3. Detect abnormal IP activity:
```
index=bootcamp_logs | stats count by ip_address, status
```

✔ Helps identify brute force attempts from specific IPs.

## 4. Build Dashboard Panels

We created a dashboard called “Login Analysis”.
Panels included:

* Pie Chart → Success vs Failure distribution.

* Bar Graph → Failed logins by username.

* Timechart → Login attempts over time.

👉 See screenshots in /screenshots

## 5. Interpret & Present Findings

From the dashboard:

* High number of failed logins from a single IP indicated possible brute-force attempts.

* Certain usernames had repeated failures, suggesting targeted attacks.

* Normal login trends could be distinguished from anomalies.
  
## 📑 Report

The detailed PDF report (with dataset, queries, analysis, and screenshots) is available here:
👉 [Download Report](https://github.com/AdarshVL/Cyber_Security_Project/blob/main/Cyber_Security_Project_Report.docx)

## 💡 Tips for Learners

 * Start with clean, structured data.

* Explore fields before writing queries.

* Begin with simple SPL, then move to advanced.

* Focus on security insights, not just visuals.

* Document everything properly.

## 🚀 Tech Stack and Tools

* Splunk Enterprise / Splunk Cloud

* SPL (Search Processing Language)

* Dataset: Structured CSV logs

## 📂 Repository Contents

* dataset/ → Sample log dataset.

* queries/ → All SPL queries with explanations.

* screenshots/ → Dashboard and panel images.

* report/ → Final project report (PDF).
