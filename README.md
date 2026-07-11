# 📦 GitHub Repository Monitor — n8n Automation

![n8n](https://img.shields.io/badge/n8n-Automation-orange)
![GitHub API](https://img.shields.io/badge/API-GitHub%20REST%20API-black)
![Telegram](https://img.shields.io/badge/Notification-Telegram-blue)
![JavaScript](https://img.shields.io/badge/Code-JSON%20Processing-yellow)
![License](https://img.shields.io/badge/license-MIT-green)

An automated GitHub repository monitoring workflow built using **n8n**, the **GitHub REST API**, **HTTP Request**, and **Telegram Bot API**.

This system automatically retrieves repository statistics at scheduled intervals, processes GitHub API responses, formats repository information into a readable report, and sends updates directly to Telegram.

**Stack:**  
n8n · GitHub REST API · HTTP Request · JSON Processing · Telegram Bot · Workflow Automation


---

# 🎯 Project Overview


## Problem

Tracking GitHub repository activity manually can become repetitive and time-consuming.

Common challenges include:

- Manually checking repository statistics
- Missing important repository updates
- No automated monitoring system
- Difficulty tracking project activity over time
- Repetitive API data checking


Common scenarios:

- Open-source project monitoring
- Personal repository tracking
- Developer activity monitoring
- Software project analytics


---

## Solution

This project creates an automated GitHub monitoring system by:


1. Running scheduled repository checks
2. Sending requests to GitHub REST API
3. Retrieving repository information
4. Processing JSON API responses
5. Formatting repository statistics
6. Sending reports through Telegram


The workflow acts as a lightweight GitHub assistant that automatically delivers repository insights without manual checking.


---

# ✨ Features


## Repository Monitoring

✅ Automated GitHub repository tracking  
✅ Repository statistics retrieval  
✅ Star and fork monitoring  
✅ Issue tracking  
✅ Last update monitoring  


## API Integration

✅ GitHub REST API integration  
✅ HTTP request automation  
✅ JSON response processing  
✅ Public API usage  


## Notifications

✅ Telegram repository reports  
✅ Scheduled updates  
✅ Real-time information delivery  


## Automation

✅ Fully automated workflow  
✅ No manual repository checking  
✅ Free GitHub API integration  


---

# 🗺️ System Architecture


```mermaid
flowchart TD

A["⏰ Schedule Trigger"]

--> B["🌐 GitHub REST API"]


B --> C["📡 HTTP Request"]


C --> D["⚙️ Edit Fields (Set)"]


D --> E["📱 Telegram Notification"]

````

---

# 🏗️ Workflow Implementation

# Workflow 1: GitHub Repository Monitoring Pipeline

## Node 1 — Schedule Trigger

### Purpose

Automatically starts the repository monitoring workflow at a configured interval.

Example Configuration:

```text
Trigger:

Every Day


Time:

08:00 AM
```

Execution Flow:

```text
Scheduled Time

      ↓

Fetch Repository Data

      ↓

Generate Report
```

---

# Node 2 — HTTP Request

### Purpose

Retrieves repository information from the GitHub REST API.

Configuration:

```text
Method:

GET


Authentication:

None


API:

GitHub REST API
```

Example Endpoint:

```text
https://api.github.com/repos/n8n-io/n8n
```

Captured Information:

| Field           | Description        |
| --------------- | ------------------ |
| Repository Name | Project name       |
| Description     | Repository summary |
| Stars           | Star count         |
| Forks           | Fork count         |
| Watchers        | Watcher count      |
| Issues          | Open issues        |
| Branch          | Default branch     |
| Updated Date    | Last update time   |

Example Response:

```json
{
"name":
"n8n",

"stars":
127532,

"forks":
38450,

"openIssues":
915,

"defaultBranch":
"master"
}
```

---

# Node 3 — Edit Fields (Set)

### Purpose

Extract and format GitHub repository information into a readable Telegram message.

Processed Data:

| Field      | Description           |
| ---------- | --------------------- |
| Repository | Repository name       |
| Stars      | Star count            |
| Forks      | Fork count            |
| Watchers   | Watch count           |
| Issues     | Open issues           |
| Branch     | Default branch        |
| URL        | Repository link       |
| Updated    | Last update timestamp |

Processing:

```text
GitHub API Response

        ↓

Selected Repository Data

        ↓

Telegram Report
```

---

# Node 4 — Telegram Notification

### Purpose

Send repository statistics directly to Telegram.

Example:

```text
📦 GitHub Repository Report


📁 Repository:

n8n-io/n8n


⭐ Stars:

127,532


🍴 Forks:

38,450


👀 Watchers:

127,532


🐞 Open Issues:

915


🌿 Default Branch:

master


📅 Last Updated:

2026-07-01T03:20:00Z


🤖 Generated automatically with n8n.
```

---

# 🔐 Credentials Required

| Service          | Purpose                 |
| ---------------- | ----------------------- |
| Telegram Bot API | Send repository reports |
| n8n Instance     | Workflow execution      |

Note:

GitHub public repositories can be accessed without authentication.

---

# ⚙️ Setup Guide

## 1. Configure Schedule Trigger

Set repository monitoring frequency.

Example:

```text
Every Day

08:00 AM
```

---

## 2. Configure GitHub HTTP Request

Add repository API endpoint.

Required:

```text
Repository Owner

Repository Name

GitHub API URL
```

Example:

```text
https://api.github.com/repos/user/project
```

---

## 3. Configure Edit Fields Node

Customize displayed information.

Available fields:

```text
Repository Name

Stars

Forks

Issues

Branch

Updated Date
```

---

## 4. Configure Telegram Bot

Steps:

1. Create Telegram bot using BotFather
2. Copy bot token
3. Add Telegram credentials in n8n
4. Configure chat ID

---

## 5. Import Workflow

Import:

```text
workflow.json
```

Configure:

* Repository URL
* Telegram credentials
* Schedule interval

Activate workflow.

---

# 🧪 Testing Checklist

| Test Case             | Expected Result       |
| --------------------- | --------------------- |
| Schedule executes     | Workflow starts       |
| HTTP Request runs     | GitHub data retrieved |
| API response received | JSON processed        |
| Edit Fields executes  | Report generated      |
| Telegram executes     | Message received      |

---

# 📁 Repository Structure

```text
GitHub-Repository-Monitor-n8n/

│
├── README.md
│
├── workflow.json
│
├── screenshots/
│
│   ├── workflow.png
│   ├── schedule-trigger.png
│   ├── http-request.png
│   ├── edit-fields.png
│   ├── telegram-output.png
│   └── workflow-execution.png
│
└── LICENSE
```

---

# 📸 Screenshots

Recommended screenshots:

* Complete workflow
* Schedule Trigger configuration
* GitHub API response
* HTTP Request node
* Edit Fields formatting
* Telegram repository report
* Workflow execution result

---

# 🚀 Future Improvements

| Feature                        | Implementation              |
| ------------------------------ | --------------------------- |
| Multiple Repository Monitoring | Track many repositories     |
| GitHub Issue Alerts            | Notify new issues           |
| Pull Request Monitoring        | Track PR activity           |
| Commit Tracking                | Monitor latest commits      |
| Release Notifications          | Detect new releases         |
| Google Sheets Logging          | Store repository history    |
| Dashboard Analytics            | Visualize repository growth |
| AI Repository Analysis         | Generate project insights   |

---

# 🎓 Skills Applied

## Automation

* n8n Workflow Automation
* Scheduled workflows
* Monitoring pipelines

## APIs

* GitHub REST API
* HTTP Requests
* JSON API processing

## Data Processing

* JSON transformation
* Data formatting
* API response handling

## Integrations

* Telegram Bot API
* GitHub API

## Business Automation

* Automated reporting systems
* Monitoring workflows
* Developer productivity tools

---

# 📚 Learning Objectives

This project demonstrates:

* Building API-powered automation systems
* Integrating external REST APIs with n8n
* Processing JSON responses
* Creating automated reporting workflows
* Building Telegram notification systems
* Designing monitoring solutions

---

# 🙌 Acknowledgements

* n8n
* GitHub REST API
* Telegram Bot API

---

# 👨‍💻 Author

**Belio C. Sinangote**

BS Information Technology Student
Cebu Technological University (CTU)

GitHub:

[https://github.com/belioautomation](https://github.com/belioautomation)

This project is part of my **30-Day n8n Automation Portfolio**, showcasing practical automation solutions using **n8n, APIs, monitoring systems, and workflow automation**.

---

# 📄 License

MIT License

```
```
