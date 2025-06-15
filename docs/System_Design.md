# 🛠️ System Design Overview

## 📐 Technical Architecture

This system is built using a combination of custom and standard Salesforce objects, intentionally designed to balance flexibility, scalability, and ease of use. Automation is implemented using declarative tools (primarily Flows), allowing even non-developers to maintain and adapt the system over time.

---

## 🔗 Key Object Relationships

- **Project (Custom Object)**  
  Serves as the central object where all initiatives are tracked.

- **Project Task (Custom Object)**  
  Linked to Projects via a lookup relationship; used to manage to-dos, milestones, and timelines.

- **User / Contact**  
  Assigned as owners to Projects and Tasks for visibility and accountability.

- **Reports & Dashboards**  
  Pull data from both Project and Task objects to support real-time visibility and decision-making.

- **Automation**  
  Uses one core Scheduled Flow to handle deadline reminders and task tracking.

---

## 🔄 Flow Automation Overview

- **Scheduled Flow: Task Reminder System**
  - Runs daily at a scheduled time.
  - Finds Project Tasks with Due Date = Tomorrow.
  - Loops through the results.
  - Sends email reminders to task owners.

This no-code automation ensures that deadlines are not missed, without relying on manual follow-ups.

---

## 📊 Visual Architecture Diagram

A high-level system diagram provides a visual understanding of how the key components interact.

📍 See `/docs/System_Architecture.png`  
Make sure this image file is uploaded in your `/docs` folder and linked in your `README.md`.

---

## ✅ Summary

This design demonstrates:
- A scalable Salesforce data model for nonprofit projects
- Automation using Flows instead of Apex
- Real-time reporting and alerting
- Lightweight architecture that’s easy to deploy and manage
