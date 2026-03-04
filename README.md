# AI-Powered Lead Qualification

An intelligent automation pipeline that scores and routes sales leads using AI, built with n8n and Python.

## Problem
Sales teams waste hours manually sorting through raw leads. This system automates the process, so they can focus on the best opportunities immediately.

## Solution
- Ingest lead data from CSV files.
- Use Groq (or Gemini) to analyze each lead and assign a relevance score.
- High‑scoring leads are sent instantly to a Telegram chat.
- Low‑scoring leads are stored for later review.

## Components
- **n8n workflow** – orchestrates the pipeline, triggers on new CSV upload.
- **Python script** – handles data cleaning and AI prompt engineering.
- **Telegram bot** – delivers real‑time alerts.

## Tech Stack
- n8n (workflow automation)
- Python (pandas, requests)
- Groq / Gemini API
- Telegram Bot API

## Setup
1. Clone this repo:  
   `git clone https://github.com/sergeykeba-cell/n8n-ai-automation-leads.git`
2. Install Python dependencies:  
   `pip install pandas requests python-telegram-bot`
3. Configure your API keys in `.env` (see `.env.example`).
4. Import the n8n workflow from `workflow.json`.
5. Upload a CSV file to the designated folder – the pipeline will run automatically.
