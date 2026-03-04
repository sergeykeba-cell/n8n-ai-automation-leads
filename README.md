AI-Driven Lead Qualification System 🚀
An intelligent automation pipeline designed to eliminate manual lead sorting. This system processes raw lead data, evaluates potential business value using LLMs (Llama 3 via Groq), and delivers actionable insights directly to sales teams.

🌟 Key Features
Automated Lead Scoring: AI analyzes lead profiles and assigns a priority score (1-10).

Instant Processing: Leverages Groq LPU for ultra-fast inference (sub-second response times).

Multi-Channel Integration: Seamless data flow between CSV files, Google Sheets, and Telegram.

Custom AI Insights: Generates personalized recommendations for sales follow-ups.

🛠 Tech Stack
Orchestration: n8n (Low-code workflow automation)

AI Engine: Groq API (Llama 3 / Mixtral)

Language: Python 3.11 (Custom data processing)

Communication: Telegram Bot API

📐 Workflow Architecture
Data Ingestion: New leads are triggered via Webhook or fetched from a CSV/Google Sheet.

Context Injection: Python scripts clean and format the data for the LLM.

AI Analysis: Groq processes the lead information based on custom Prompt Engineering templates.

Distribution: High-priority leads are sent to Telegram; all logs are saved to a CRM or Database.

🚀 Getting Started
Prerequisites
Python 3.11+

n8n (Desktop or Cloud version)

API Keys for Groq and Telegram (BotFather)

Installation
Clone the repo:

Bash
git clone https://github.com/sergeykeba-cell/n8n-ai-automation-leads.git
cd n8n-ai-automation-leads
Set up Virtual Environment:

Bash
python3.11 -m venv .venv
source .venv/bin/activate  # On Windows use `.venv\Scripts\activate`
pip install -r requirements.txt
Configure Environment Variables:
Create a .env file:

Фрагмент кода
GROQ_API_KEY=your_key_here
TELEGRAM_BOT_TOKEN=your_token_here
Importing n8n Workflow
Open n8n.

Import the automation/workflow_leads.json file.

Update the credentials for Groq and Telegram nodes.

🔒 Security Note
This repository contains no real user data. All CSV files in data/ are samples generated for demonstration purposes. Never commit your .env file or real lead databases to GitHub.

👨‍💻 Author
Sergey Keba

LinkedIn: Junior AI Automation Engineer

Telegram: @SergieyKeba
