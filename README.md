🛡️ Splunk Log Analysis & Cybersecurity Monitoring Portfolio

A comprehensive portfolio demonstrating advanced skills in Splunk Enterprise, Search Processing Language (SPL), and security log analysis across multiple network protocols. This collection highlights expertise in threat hunting, anomaly detection, event classification, and SIEM workflows using real-world log data.

👨‍💻 About This Portfolio

This repository contains documentation, SPL queries, and analysis results for four end-to-end cybersecurity monitoring projects.
Each project transforms raw logs into actionable intelligence, showcasing both blue-team and SOC-ready capabilities.

Primary Tool: Splunk Enterprise 10.0.1
Skills Demonstrated: SPL Mastery, Regex Field Extraction, Threat Hunting, Event Classification, SIEM Operations
Prepared By: Pranit Kalambate
Training: CEH Curriculum / Cybersecurity Analyst Training

📁 Project List
1️⃣ DNS Log Analysis & Threat Hunting

Security assessment focused on DNS traffic—a common vector for C2 communication, DNS tunneling, and DGA malware.

🔍 Key Techniques

FQDN Extraction: Built custom field extraction to normalize DNS domain analysis.

DGA Detection: Used

stats dc(fqdn) by src_ip


to identify “Chatty Hosts” contacting abnormally high numbers of domains.

Covert Channel Detection: Leveraged

rare query_type


to reveal suspicious queries (TXT, AAAA) linked to evasion or tunneling.

📂 Repository Folder

01_DNS_Log_Analysis/

-Screenshots

-ADVANCED DNS SECURITY MONITORING WITH SPLUNK (PDF)

-splunk_queries.txt

2️⃣ HTTP Log Analysis & Web Security Monitoring

Analysis of web server access logs to identify unauthorized access, bruteforce attempts, and high-risk endpoints.

🔍 Key Techniques

Baseline Traffic Analysis: Observed patterns across HTTP methods (GET, POST, HEAD).

Unauthorized Access Detection:

status=401 OR status=403


combined with top uri to detect targeted paths like /admin, /phpmyadmin.

Firewall-Ready Intelligence: Isolated offending src_ip addresses for potential blocking.

📂 Repository Folder

02_HTTP_Log_Analysis/

-Screenshots

-HTTP LOG ANALYSIS AND WEB SECURITY MONITORING (PDF)

-splunk_queries.txt

3️⃣ FTP Log Analysis & File Integrity Monitoring

Focused on tracking file uploads, deletions, and authorization errors to detect integrity issues.

🔍 Key Techniques

Regex-Based Field Extraction: Parsed username, command, response_code, etc.

File Integrity Monitoring: Monitored STOR (upload) and DELE (delete) activities.

Incident Identification: Found a critical case where a user consistently triggered response_code=400 failures.

📂 Repository Folder

03_FTP_Log_Analysis/

-Screenshots

-FTP LOG ANALYSIS AND FILE INTEGRITY MONITORING PROJECT (PDF)

-splunk_queries.txt


4️⃣ SSH Brute-Force Detection & SIEM Workflow

Simulated a Mini-SIEM by ingesting Linux authentication logs using a Splunk Universal Forwarder.

🔍 Key Techniques

End-to-End Log Ingestion: Forwarded /var/log/auth.log from Kali Linux to Splunk.

Risk-Based Event Categorization:
Low Risk (Priority 8): Failed attempts targeting invalid users.
High Risk (Priority 3): Failed attempts against valid system accounts.

SOC-Ready Searches: Rapid isolation of targeted brute-force attacks.

📂 Repository Folder

04_SSH_Brute_Force_Detection/

-Screenshots

-SPLUNK EVENT TYPE PROJECT REPORT (PDF)

-splunk_queries.txt


📊 Dashboards & Results

Each project includes Splunk dashboards converting raw logs into clear visual insights:

Finding	Description
Top Potential DGA Hosts	Highlights clients querying unusually high numbers of domains — often linked to DGA malware.
Top IPs Generating Web Auth Failures	Identifies systems attempting repeated unauthorized access to web resources (401/403).
Users with Critical FTP Command Failures	Tracks file integrity issues by monitoring failed STOR/DELE operations.
SSH Brute-Force Risk Assessment	Categorizes SSH attack attempts into High vs Low priority for SOC triage.🛡️ Splunk Log Analysis & Cybersecurity Monitoring Portfolio

A comprehensive portfolio demonstrating advanced skills in Splunk Enterprise, Search Processing Language (SPL), and security log analysis across multiple network protocols. This collection highlights expertise in threat hunting, anomaly detection, event classification, and SIEM workflows using real-world log data.

👨‍💻 About This Portfolio

This repository contains documentation, SPL queries, and analysis results for four end-to-end cybersecurity monitoring projects.
Each project transforms raw logs into actionable intelligence, showcasing both blue-team and SOC-ready capabilities.

Primary Tool: Splunk Enterprise 10.0.1
Skills Demonstrated: SPL Mastery, Regex Field Extraction, Threat Hunting, Event Classification, SIEM Operations
Prepared By: Pranit Kalambate
Training: CEH Curriculum / Cybersecurity Analyst Training

📁 Project List
1️⃣ DNS Log Analysis & Threat Hunting

Security assessment focused on DNS traffic—a common vector for C2 communication, DNS tunneling, and DGA malware.

🔍 Key Techniques

FQDN Extraction: Built custom field extraction to normalize DNS domain analysis.

DGA Detection: Used

stats dc(fqdn) by src_ip


to identify “Chatty Hosts” contacting abnormally high numbers of domains.

Covert Channel Detection: Leveraged

rare query_type


to reveal suspicious queries (TXT, AAAA) linked to evasion or tunneling.

📂 Repository Folder

01_DNS_Log_Analysis/

-Screenshots

-ADVANCED DNS SECURITY MONITORING WITH SPLUNK (PDF)

-splunk_queries.txt

2️⃣ HTTP Log Analysis & Web Security Monitoring

Analysis of web server access logs to identify unauthorized access, bruteforce attempts, and high-risk endpoints.

🔍 Key Techniques

Baseline Traffic Analysis: Observed patterns across HTTP methods (GET, POST, HEAD).

Unauthorized Access Detection:

status=401 OR status=403


combined with top uri to detect targeted paths like /admin, /phpmyadmin.

Firewall-Ready Intelligence: Isolated offending src_ip addresses for potential blocking.

📂 Repository Folder

02_HTTP_Log_Analysis/

-Screenshots

-HTTP LOG ANALYSIS AND WEB SECURITY MONITORING (PDF)

-splunk_queries.txt

3️⃣ FTP Log Analysis & File Integrity Monitoring

Focused on tracking file uploads, deletions, and authorization errors to detect integrity issues.

🔍 Key Techniques

Regex-Based Field Extraction: Parsed username, command, response_code, etc.

File Integrity Monitoring: Monitored STOR (upload) and DELE (delete) activities.

Incident Identification: Found a critical case where a user consistently triggered response_code=400 failures.

📂 Repository Folder

03_FTP_Log_Analysis/

-Screenshots

-FTP LOG ANALYSIS AND FILE INTEGRITY MONITORING PROJECT (PDF)

-splunk_queries.txt


4️⃣ SSH Brute-Force Detection & SIEM Workflow

Simulated a Mini-SIEM by ingesting Linux authentication logs using a Splunk Universal Forwarder.

🔍 Key Techniques

End-to-End Log Ingestion: Forwarded /var/log/auth.log from Kali Linux to Splunk.

Risk-Based Event Categorization:
Low Risk (Priority 8): Failed attempts targeting invalid users.
High Risk (Priority 3): Failed attempts against valid system accounts.

SOC-Ready Searches: Rapid isolation of targeted brute-force attacks.

📂 Repository Folder

04_SSH_Brute_Force_Detection/

-Screenshots

-SPLUNK EVENT TYPE PROJECT REPORT (PDF)

-splunk_queries.txt


📊 Dashboards & Results

Each project includes Splunk dashboards converting raw logs into clear visual insights:

Finding	Description
Top Potential DGA Hosts	Highlights clients querying unusually high numbers of domains — often linked to DGA malware.
Top IPs Generating Web Auth Failures	Identifies systems attempting repeated unauthorized access to web resources (401/403).
Users with Critical FTP Command Failures	Tracks file integrity issues by monitoring failed STOR/DELE operations.
SSH Brute-Force Risk Assessment	Categorizes SSH attack attempts into High vs Low priority for SOC triage.
