# 🛠️ Admin Setup Guide

This guide is intended for Salesforce Admins to configure, maintain, and troubleshoot the Nonprofit Project Management System. It covers how to access and adjust the flows, email templates, custom objects, and other system components.

---

## 🔁 Scheduled Flow: Task Reminder System

### 📍 Location
- Setup → Flows → `Scheduled Task Reminder`

### 🔧 Flow Overview
- **Type**: Scheduled Flow
- **Frequency**: Daily
- **Trigger Time**: 6 AM daily (adjustable)
- **Purpose**: Sends email reminders for Tasks due tomorrow

### 📌 Variables Used
| Variable API Name | Type      | Description                           |
|-------------------|-----------|---------------------------------------|
| `varTomorrow`     | Date      | Stores tomorrow's date                |
| `varDueTask`      | Record    | Holds current Task record in loop     |

---

## 📨 Email Template

### 📍 Location
- App Launcher → Email Templates → `Task Reminder Alert`

### 💡 Template Details
- Type: Lightning Email Template
- Folder: Public Email Templates
- Merge Fields: {!Task.Subject}, {!Task.Due_Date__c}

---

## 🧱 Custom Objects

### Project
- API Name: `Project__c`
- Description: Main object for tracking nonprofit initiatives

### Project Task
- API Name: `Project_Task__c`
- Child of: Project
- Includes: Due Date, Status, Owner, Reminder Sent

---

## 📊 Reports & Dashboards

### Report
- Name: `Upcoming Tasks by Project`
- Filters: Task Due Date = Next 7 Days

### Dashboard
- Name: `Nonprofit Projects Overview`
- Components: Tasks Due, Projects by Status, Impact Metrics

---

## 🔍 Debug Tips

- Use **Flow Debug Mode** for testing scheduled automation
- Check **Email Logs** if reminders are not being sent
- Make sure scheduled flow is **Activated** (not just saved)

---

## 🔁 Editable Fields

Admins can adjust the following:
- Reminder email content
- Flow scheduled start time
- Filter criteria in Get Records element
- Dashboard filters and visibility

---

## 🔒 Security & Access

- Profiles: Assign custom profiles with access to Project and Task objects
- Field-Level Security: Ensure key fields like Due Date and Reminder Sent are visible
- Sharing Rules: Use criteria-based sharing for Project object if needed

---

## ✅ Maintenance Checklist

- [ ] Update reminder email if messaging changes
- [ ] Add new Task Status values as needed
- [ ] Expand automation to other Task types
- [ ] Review field history tracking quarterly

---

_Last updated: June 2025_
