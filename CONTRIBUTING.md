# Contributing to n8n-ai-automation-leads

Thanks for considering a contribution! This project is small and pragmatic — contributions of any size are welcome, from fixing a typo in the README to adding a new lead-scoring strategy.

## Ways to contribute

- 🐛 Report bugs via [Issues](https://github.com/sergeykeba-cell/n8n-ai-automation-leads/issues) using the bug report template.
- 💡 Suggest features or new integrations (e.g. Slack instead of Telegram, other LLM providers).
- 🧠 Improve the n8n workflow (`workflows/n8n-ai-automation-leads.json`) — new nodes, better error handling, retries.
- 🐍 Improve the Python scoring/cleaning script — tests, type hints, edge-case handling.
- 📚 Improve documentation — the README, this file, or inline comments.

## Local development setup

1. Fork and clone the repo.
2. Copy `.env.example` to `.env` and fill in test API keys (a free-tier Groq key is enough for local testing).
3. Start n8n locally:
   ```bash
   docker-compose up
   ```
4. Install Python dependencies:
   ```bash
   pip install -r requirements.txt
   ```
5. Run the scoring script against the sample data:
   ```bash
   python scripts/score_leads.py --input data/sample_leads.csv
   ```

## Code style

- Python code should be formatted with [`black`](https://github.com/psf/black) and pass [`ruff`](https://github.com/astral-sh/ruff) linting.
- Public functions should have docstrings and type hints.
- Keep the n8n workflow JSON changes minimal and export it directly from the n8n UI (**Download** button) to avoid unrelated diffs.

## Submitting a pull request

1. Create a branch from `main`: `git checkout -b feat/short-description`.
2. Make your changes, and make sure the CI checks (lint + workflow JSON validation) pass locally where possible.
3. Fill in the PR template — describe *what* changed and *why*.
4. Link any related issue.

## Code of Conduct

By participating in this project, you agree to abide by our [Code of Conduct](CODE_OF_CONDUCT.md).
