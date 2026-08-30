
## Components

| Component | Role |
|---|---|
| **n8n workflow** (`workflows/n8n-ai-automation-leads.json`) | Orchestrates the pipeline, triggers on new CSV upload |
| **Python script** (`scripts/`) | Handles data cleaning and AI prompt engineering |
| **Telegram bot** | Delivers real-time alerts for high-scoring leads |

## Tech stack

- [n8n](https://n8n.io) — workflow automation (tested on n8n `1.6x`+)
- Python 3.10+ (`pandas`, `requests`)
- Groq / Gemini API
- Telegram Bot API

## Quick start (Docker — recommended)

```bash
git clone https://github.com/sergeykeba-cell/n8n-ai-automation-leads.git
cd n8n-ai-automation-leads
cp .env.example .env        # fill in your API keys
docker-compose up
```

n8n will be available at `http://localhost:5678`. Import the workflow from
`workflows/n8n-ai-automation-leads.json` via **Workflows → Import from File**.

## Manual setup (without Docker)

1. Clone this repo:
```bash
   git clone https://github.com/sergeykeba-cell/n8n-ai-automation-leads.git
   cd n8n-ai-automation-leads
```
2. Install Python dependencies:
```bash
   pip install -r requirements.txt
```
3. Configure your API keys:
```bash
   cp .env.example .env
   # then edit .env with your GROQ_API_KEY / TELEGRAM_BOT_TOKEN / TELEGRAM_CHAT_ID
```
4. Import the n8n workflow from `workflows/n8n-ai-automation-leads.json` into your local or cloud n8n instance.
5. Drop a CSV file into the designated folder — the pipeline runs automatically.

A sample file is provided at `data/sample_leads.csv` so you can test the pipeline immediately without your own data.

## Configuration

All secrets are read from environment variables — see [`.env.example`](.env.example) for the full list.

## Contributing

Contributions are welcome! Please read [`CONTRIBUTING.md`](CONTRIBUTING.md) before opening a PR, and check open [issues](https://github.com/sergeykeba-cell/n8n-ai-automation-leads/issues) for ways to help.

## License

Released under the [MIT License](LICENSE).

## About

Автоматизація обробки лідів з CSV-файлу для бізнесу (CRM, продажі).
