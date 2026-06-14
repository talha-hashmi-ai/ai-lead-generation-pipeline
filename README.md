# 🤖 AI Lead Generation Pipeline

> Automated B2B outreach pipeline built with n8n, OpenAI GPT-4o-mini, Apollo.io, Gmail and Google Sheets

![n8n](https://img.shields.io/badge/n8n-Automation-orange)
![OpenAI](https://img.shields.io/badge/OpenAI-GPT--4o--mini-blue)
![Apollo.io](https://img.shields.io/badge/Apollo.io-Lead%20Sourcing-purple)
![Gmail](https://img.shields.io/badge/Gmail-Email%20Delivery-red)
![Google Sheets](https://img.shields.io/badge/Google%20Sheets-CRM-green)

---

## 📌 What It Does

This pipeline automates the entire B2B outreach process — from lead sourcing to personalized email delivery — without any manual intervention.

**Target use case:** Reaching Amazon FBA founders, brand owners, and eCommerce entrepreneurs at scale.

---

## 🔄 Pipeline Stages

| Stage | Node | Description |
|-------|------|-------------|
| 1 | HTTP Request | Fetches contacts from Apollo.io via REST API |
| 2 | Split Out | Splits contact array into individual leads |
| 3 | Google Sheets | Loads previously contacted leads for dedup |
| 4 | Merge | Filters out already-contacted leads |
| 5 | AI Agent (GPT-4o-mini) | Generates personalized email per lead |
| 6 | Google Sheets | Logs each lead with timestamp and status |
| 7 | Gmail | Sends personalized email automatically |

---

## 🛠️ Tech Stack

- **Automation Engine:** n8n (Docker, localhost:5678)
- **Lead Source:** Apollo.io (contacts/search API)
- **AI Model:** OpenAI GPT-4o-mini
- **Email Delivery:** Gmail (Google OAuth)
- **CRM/Tracker:** Google Sheets
- **Deduplication:** n8n Merge node (field matching on email)

---

## ⚡ Key Features

- Fully automated end-to-end pipeline
- AI-personalized emails per contact (name, title, company)
- Built-in deduplication — no lead contacted twice
- Audit trail in Google Sheets with timestamps
- Modular design — each stage independently swappable

---

## 📁 Repository Structure

---

## 🚀 How To Run

1. Install n8n via Docker:
```bash
docker run -it --rm --name n8n -p 5678:5678 -v n8n_data:/home/node/.n8n docker.n8n.io/n8nio/n8n
```
2. Import `workflow/lead_gen_pipeline.json` into n8n
3. Add credentials: Apollo.io API key, OpenAI API key, Gmail OAuth, Google Sheets OAuth
4. Create a Google Sheet named "Lead Tracker Apollo" with columns: Email, Name, Company, Status, Date Contacted
5. Click "Execute workflow"

---

## 👤 Built By

**Talha Hashmi** — AI Automation Engineer  
[LinkedIn](https://linkedin.com/in/talha-hashmi-ai) | [Himalayas](https://himalayas.app/@talhahashmi)
