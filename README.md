# Splunk-Log-Analysis-and-Cybersecurity-Monitoring-Portfolio
A portfolio showcasing proficiency in Splunk Enterprise Search Processing Language (SPL) for network security analysis, threat hunting, and infrastructure monitoring across DNS, HTTP, and FTP protocols.

# 🛡️ Splunk Log Analysis and Cybersecurity Monitoring Portfolio

## 👨‍💻 Project Overview

This repository contains documentation, key Search Processing Language (SPL) queries, and analysis results for three distinct projects focused on leveraging Splunk Enterprise to transform raw log data into actionable security and operational intelligence. These projects demonstrate advanced skills in log parsing, anomaly detection, and security best practices.

* **Primary Tool:** Splunk Enterprise (Version 10.0.1)
* **Core Skills:** SPL Mastery, Field Extraction (UI & Regex), Threat Hunting, Anomaly Detection, File Integrity Monitoring.
* **Prepared By:** PRANIT KALAMBATE
* **Training:** Trained in CEH Curriculum / Cybersecurity Analyst Training

---

## 1. Project: DNS Log Analysis and Threat Hunting

This project focused on the security analysis of DNS traffic, a critical vector for command-and-control (C2) communication.

### Key Analysis Techniques:
* **Data Enrichment:** Successfully extracted the Fully Qualified Domain Name (`fqdn`) to enable domain-level analysis.
* **DGA Malware Detection:** Used the `stats dc(fqdn) by src_ip` technique to identify "Chatty Hosts" exhibiting behavior indicative of **Domain Generation Algorithm (DGA)** malware.
* **C2 Evasion Detection:** Employed the **`rare query_type`** command to find the least common DNS record types (e.g., `TXT`, `AAA`), which often signal covert communication or DNS Tunneling attempts.

### 📂 Repository Structure:
* `01_DNS_Log_Analysis/`
    * [View Full Project Documentation (PDF)] 01_DNS_Log_Analysis/ADVANCED DNS SECURITY MONITORING WITH SPLUNK SPL.pdf
    * `splunk_queries.txt` (All key SPL commands)

---

## 2. Project: HTTP Log Analysis and Web Security Monitoring

This project focused on analyzing web server access logs to assess server health and detect web application security threats.

### Key Analysis Techniques:
* **Baseline Analysis:** Established baseline traffic patterns by analyzing the frequency of HTTP Methods (GET, POST, HEAD) and most popular URIs.
* **Failed Access Monitoring:** Used targeted filtering (`status=401 OR status=403`) combined with `top uri` to identify high-risk paths being targeted by brute-force or directory enumeration attempts (`/admin`, `/phpmyadmin`).
* **Actionable Intelligence:** Identified the exact `src_ip` addresses responsible for generating unauthorized access errors, providing immediate data for firewall blocking.

### 📂 Repository Structure:
* `02_HTTP_Log_Analysis/`
    * [View Full Project Documentation (PDF)] 02_HTTP_Log_Analysis/HTTP LOG ANALYSIS AND WEB SECURITY MONITORING PROJECT.pdf
    * `splunk_queries.txt` (All key SPL commands)

---

## 3. Project: FTP Log Analysis and File Integrity Monitoring

This project focused on monitoring the FTP protocol, specifically for unauthorized file transfers, deletions, and failures that compromise file integrity.

### Key Analysis Techniques:
* **Advanced Field Extraction:** Used an **Inline Regular Expression** to precisely parse fields including `username`, `command`, and `response_code`, showcasing strong regex skills.
* **File Integrity Monitoring:** Tracked high-risk commands (`STOR` for uploads and `DELE` for deletions) to audit all user file management activity.
* **Incident Diagnosis:** Identified a critical operational failure where the primary user failed *all* upload and delete attempts (`response_code=400`), immediately linking the failures back to the responsible user (`stats count by username`).

### 📂 Repository Structure:
* `03_FTP_Log_Analysis/`
    * [View Full Project Documentation (PDF)] 03_FTP_Log_Analysis/FTP LOG ANALYSIS AND FILE INTEGRITY MONITORING PROJECT.pdf
    * `splunk_queries.txt` (All key SPL commands)

---
## 📊 Project Results: Dashboards

These images show the key findings and results from my analysis. They turn the raw log data into simple visuals that highlight security risks and issues.

| Finding | Screenshot | Project Context |
| :--- | :--- | :--- |
| **Top Potential DGA Hosts** | [![Top Potential DGA Hosts](Dashboard/DNS_dashboard.png)](Dashboard/DNS_dashboard.png) | **DNS Security:** Which client machines are connecting to the most unique domains? This helps find potential malware (DGA) that communicates with many different, suspicious domains. |
| **Top IPs Generating Web Auth Failures (401/403)** | [![Top IPs Generating Web Auth Failures](Dashboard/HTTP_dashboard.png)](Dashboard/HTTP_dashboard.png) | **Web Security:** The specific computers (Source IPs) that are failing to log in or access restricted web pages. These are the immediate targets we need to block. |
| **Top Users with Critical FTP Command Failures** | [![Top Users with Critical FTP Command Failures](Dashboard/FTP_dashboard.png)](Dashboard/FTP_dashboard.png) | **FTP/File Integrity:** A simple view of which users are causing the most critical errors when trying to upload or delete files. In this case, one user failed over 2,700 times due to a setup mistake. |
| **SSH Brute-Force Risk Assessment** | [![SSH Brute-Forcer High vs. Low Risk](Dashboard/SSH_dashboard.png)](Dashboard/SSH_dashboard.png) | **Host Security:** A quick way to sort SSH login attacks into two groups: high priority (High-Risk) and low priority (Low-Risk), so the team knows what to fix first. |

---
## ✅ What You Should Add Next

To make this repository absolutely ready for a recruiter review, ensure you add the following files to their respective project folders:

1.  **Documentation:** The finalized Word/PDF document for each project (e.g., `DNS_Analysis_Documentation.pdf`).
2.  **SPL Query Files:** Create a simple text file (`splunk_queries.txt`) in each folder containing *only* the final, working SPL commands used in that project.
3.  **Screenshots:** Include the original screenshots in a `screenshots/` folder within each project directory for visual validation of your results.
