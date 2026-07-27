# 🛡️ SSH Log Analysis using Splunk

> A Security Operations Center (SOC) project for monitoring SSH authentication events, detecting brute-force attacks, and investigating suspicious login activity using Splunk Enterprise.

---

## 📌 Project Overview

This project demonstrates how **Splunk Enterprise** can be used to analyze Linux SSH authentication logs in a SOC environment. The dashboard provides real-time visibility into login activities, highlights suspicious authentication attempts, identifies potential brute-force attacks, and visualizes attack sources geographically.

---

## 🚀 Dashboard Features

✅ Total SSH Events

✅ Successful Login Monitoring

✅ Failed Login Monitoring

✅ Connection Without Authentication Detection

✅ Failed Logins by Username

✅ Brute Force Attack Detection

✅ Attack Source IP Analysis

✅ Geographic Attack Visualization

✅ Interactive Splunk Dashboard

---

## 🛠️ Technology Stack

| Technology | Purpose |
|------------|---------|
| Splunk Enterprise | SIEM Platform |
| SPL | Search Processing Language |
| Linux SSH Logs | Log Source |
| GeoIP Lookup | Attack Geolocation |
| JSON | Log Format |

---

## 📂 Repository Structure

```text
SSH-Log-Analysis-Splunk
│
├── dashboards/
│   └── ssh_dashboard.xml
│
├── sample_logs/
│   └── ssh_log.json
│
├── screenshots/
│   └── dashboard.png
│
├── spl_queries/
│   ├── brute_force_detection.spl
│   ├── failed_logins.spl
│   ├── successful_logins.spl
│   └── geolocation.spl
│
└── README.md
```

---

# 🔍 Sample SPL Queries

## Failed Login Attempts

```spl
index=ssh auth_success=false
| stats count by username
| sort -count
```

---

## Successful Logins

```spl
index=ssh auth_success=true
| stats count
```

---

## Possible Brute Force Detection

```spl
index=ssh auth_success=false
| stats count by id.orig_h
| where count > 5
| sort -count
```

---

## Geographic Attack Map

```spl
index=ssh auth_success=false
| iplocation id.orig_h
| geostats count by Country
```

---

# 📊 Dashboard Metrics

| Metric | Description |
|---------|-------------|
| Total Events | Total SSH events ingested |
| Successful Logins | Authenticated users |
| Failed Logins | Invalid authentication attempts |
| Unauthenticated Connections | SSH connections without login |
| Top Targeted Users | Most attacked usernames |
| Brute Force Sources | IPs exceeding login threshold |
| Geo Map | Countries generating attacks |

---

# 🎯 Skills Demonstrated

- SIEM Monitoring
- Splunk Dashboard Development
- SPL Query Writing
- SSH Log Analysis
- Linux Log Investigation
- Threat Hunting
- Brute Force Detection
- Security Monitoring
- Incident Investigation
- Log Visualization

---

# 📈 Future Enhancements

- Real-time Email Alerts
- Risk-Based Alerting
- MITRE ATT&CK Mapping
- Splunk Enterprise Security Integration
- Threat Intelligence Enrichment
- Automated Incident Response
- Detection Rules
- Correlation Searches

---

# 📚 Learning Outcomes

✔ Linux Authentication Log Analysis

✔ SIEM Dashboard Development

✔ SPL Query Optimization

✔ Brute Force Detection

✔ Threat Investigation

✔ SOC Monitoring Workflow

---

## ⭐ If you found this project useful, consider giving it a star!
