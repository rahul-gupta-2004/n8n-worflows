
# Local AI RSS-to-Telegram News Brief

A fully self-hosted n8n workflow that aggregates tech RSS feeds, filters and summarizes them using a local LLM (Ollama), and delivers a clean, emoji-free news brief directly to your Telegram chat.

---

## Architecture & Tech Stack

* **Automation Engine:** n8n (running in Docker)
* **Local LLM:** Ollama (`llama3.2:1b`)
* **Data Sources:** Tech RSS Feeds (OpenAI, The Verge, Wired, etc.)
* **Notification Channel:** Telegram Bot API

---

## Workflow Pipeline

`Schedule Trigger` ➡️ `RSS Feed Readers` ➡️ `Merge & Sort` ➡️ `Limit` ➡️ `Aggregate` ➡️ `Ollama (Message a Model)` ➡️ `Clean Text` ➡️ `Telegram (Send Message)`

---

## How to Import & Setup

1. **Download the JSON:** Download `workflow.json` from this repository.
2. **Import into n8n:** Open your n8n dashboard, create a new workflow, click the options menu (`...`), and select **Import from File**.
3. **Configure Credentials:**
   * **Telegram:** Connect your Telegram Bot API token (via BotFather).
   * **Ollama:** Ensure your local Ollama instance is accessible on your Docker network (using `llama3.2:1b`).
4. **Update Chat ID:** Open the Telegram node and update the `Chat ID` field with your personal Telegram numeric ID.
5. **Activate:** Toggle the workflow active or test it using **Execute Workflow**.
