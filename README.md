SSH Log Analysis using Splunk

Monitor and investigate SSH authentication events using Splunk Enterprise. This project demonstrates how a Security Operations Center (SOC) analyst can detect brute-force attacks, monitor login activity, identify suspicious usernames, and visualize attack sources geographically.

Features
Total SSH Events
Successful Login Count
Failed Login Count
Connection Without Authentication
Failed Logins by Username
Possible Brute Force Attack Detection
Geographic Attack Map
Interactive Dashboard
Technologies
Splunk Enterprise
SPL (Search Processing Language)
Linux SSH Logs
GeoIP Lookup
JSON Log Ingestion

Example:

Sample SPL Queries
Failed Logins
index=ssh auth_success=false
| stats count by username
| sort -count
Successful Logins
index=ssh auth_success=true
| stats count
Possible Brute Force
index=ssh auth_success=false
| stats count by id.orig_h
| where count>5
| sort -count
Geo-location
index=ssh auth_success=false
| iplocation id.orig_h
| geostats count by Country
Dashboard Preview

Add the screenshot you shared:


Dataset
sample_logs/ssh_log.json
Skills Demonstrated
Log Analysis
SIEM Monitoring
SPL Query Writing
SSH Security Monitoring
Brute Force Detection
Threat Hunting
Dashboard Development
Incident Investigation
Future Improvements
Email Alerts
Risk Scoring
MITRE ATT&CK Mapping
Correlation Searches
Splunk Enterprise Security Integration
