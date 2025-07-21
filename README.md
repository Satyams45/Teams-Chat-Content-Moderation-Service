# 🛡️ Teams Chat Content Moderation Service – CST8917 Lab 3

This project implements a Microsoft Teams chat content moderation service using Azure Logic Apps. It monitors messages in real-time, analyzes them for inappropriate content, and sends email alerts when a violation is detected.

---

## 📋 Flowchart

![Moderation Flowchart](./screenshots/moderation-flowchart.png)

---

## ⚙️ Logic App Workflow Overview

### **Trigger:**
- **Microsoft Teams** — Triggered when a new message is posted in a selected channel.

### **Workflow:**
1. **Teams Trigger**: Detects new messages in the channel.
2. **[Optional] Azure Function**: Preprocess the message (e.g., sanitize content).
3. **[Optional] Azure Content Moderator**: Checks for offensive language or policy violations.
4. **Condition**: Evaluates if message violates content policy.
5. **Email Notification**: Sends an email to an admin with message details.

---

## 🧠 Optional Integrations

### **Azure Function**
- A Python/JavaScript function to clean and process Teams message before analysis.

### **Azure Cognitive Services**
- Uses the Content Moderator or Language API to analyze message content using AI/NLP.

---

## 🧪 Testing

### **Test Cases:**
- ✅ Normal messages: No alert.
- ❌ Inappropriate messages: Trigger alert.

### **Verification:**
- Message with flagged content triggers email to administrator.
- Functions and Cognitive Services (if used) process and return expected output.

---

## ⚠️ Challenges & Resolutions

| Challenge | Resolution |
|----------|-------------|
| Logic App permission to Teams | Ensured correct Teams connector and user consent |
| Keyword detection too basic | Integrated Content Moderator API for better accuracy |
| Delay in triggers | Used Teams channel with active flow for real-time testing |

---

## 🚀 Future Improvements

- Integrate a dashboard for message logging and analytics.
- Use Azure OpenAI for smarter, contextual moderation.
- Add severity scoring and escalation workflow.

---

## 📁 Repository Structure

```
📁 root/
├── LogicApp.json               # Exported Logic App definition
├── azure-function/             # Optional: Azure Function code
├── screenshots/
│   └── moderation-flowchart.png
├── README.md                   # Project Documentation (This file)
```

---
