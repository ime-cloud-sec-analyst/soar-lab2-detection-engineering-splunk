# soar-lab2-detection-engineering-splunk
This lab demonstrates Detection Engineering in Splunk using real-time phishing data logs. It builds on Part 1 (Phishing Triage) and walks through configuring data inputs, setting sourcetypes, executing detection rules, managing Splunk storage, and recognizing platform limitations when working with free-tier environments. 
# 🧠 SOAR Lab 2: Detection Engineering in Splunk

**Author**: Dr. Ime Ben  
**GitHub Handle**: [`@ime-cloud-sec-analyst`](https://github.com/ime-cloud-sec-analyst)  
**Lab Focus**: Security Orchestration, Automation, and Response (SOAR) – Detection Engineering  
**Part 2 of SOAR Lab Series**

---

## 📘 Overview

This lab builds on [**Part 1: Phishing Triage**](https://github.com/ime-cloud-sec-analyst/soar-lab1-phishing-triage), diving into the detection phase using **Splunk Enterprise**. The goal is to create, test, and analyze detection rules that identify phishing activities by ingesting and querying custom logs.

---

## 🎯 Objectives

- ✅ Launch and configure a Splunk Enterprise instance on AWS EC2  
- ✅ Add and label custom phishing logs with sourcetype `phishing_logs_source`  
- ✅ Search and analyze logs using Splunk Search & Reporting app  
- ✅ Simulate detection engineering activities for SIEM/SOAR workflows  
- ✅ Document platform constraints and performance under free-tier limits  

---

## 🖼️ Screenshot Documentation (27 Images)

All lab steps have been documented with 27 screenshots. These include:

1. **Splunk Login & Dashboard Access**
2. **AWS EC2 Instance Configuration**
3. **Splunk Daemon Start Logs**
4. **Phishing Log Source Configuration**
5. **Data Ingestion Steps**
6. **Search Query Attempt**  
7. **Error Handling: Disk Quota Limit**
8. **GitHub Repository Creation & Export**

> All images are saved in `/screenshots/` folder (to be uploaded).

---

## 🔍 Query Executed

```spl
index=default sourcetype="phishing_logs_source"
This query was intended to fetch phishing logs from the custom sourcetype we ingested. However, due to free-tier disk space limits in Splunk, the query was blocked.

⚠️ Observed Limitations
❌ Search Not Executed:
The following error was encountered while running queries:

swift
Copy
Edit
The minimum free disk space (5000MB) reached for /opt/splunk/var/run/splunk/dispatch.
🧩 Root Cause:
Splunk free edition has a dispatch directory limit of 5000MB

No room left to execute new search jobs

🛠️ Suggested Fixes (For Future Labs):
Upgrade to Splunk Enterprise Trial or manage dispatch cleanup (btool, clean-dispatch)

Use external volume mount to extend /opt/splunk/ disk

Integrate with S3 or CloudWatch for external log management

🧠 Learning Outcomes
Hands-on familiarity with Splunk's ingestion and detection engine

Experience setting up custom sourcetypes and running structured queries

Awareness of technical limitations in free-tier instances and how to mitigate them in enterprise settings

📎 Related Lab
👉 SOAR Lab 1 – Phishing Triage in Splunk

👤 Author Info
Dr. Ime Ben
Cloud Security Analyst | AWS & Azure Certified | Cybersecurity GRC | GitHub: @ime-cloud-sec-analyst
Email: imegcu55@gmail.com
GitHub Lab Series: SOAR Labs

