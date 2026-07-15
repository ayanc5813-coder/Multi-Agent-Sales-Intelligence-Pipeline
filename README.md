# 🚀 Multi-Agent Sales Intelligence Pipeline

[![Python 3.10+](https://img.shields.io/badge/python-3.10+-blue.svg)](https://www.python.org/downloads/)
[![Strands Agents](https://img.shields.io/badge/Strands-Agents_SDK-orange.svg)](https://github.com/strands-agents)
[![Gradio](https://img.shields.io/badge/Gradio-6.0-green.svg)](https://gradio.app/)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

An automated, open-source AI sales prospect discovery and outreach pipeline. Instead of relying on a single LLM to perform complex workflows, this project routes tasks through a **Graph-based Multi-Agent System**.

It monitors social signals, enriches company profiles, scores lead intent, and drafts personalized B2B outreach emails based strictly on structured data.

---

## 🌟 How It Works (The Architecture)

The system breaks down the sales research workflow into four specialized agents, orchestrated sequentially. 

1. **🕵️ Trend Agent:** Scans recent web data for launches, GitHub activity, or social discussions (Reddit, Hacker News) to find active signals.
2. **🏢 Search Agent:** Gathers foundational company context, such as size, tech stack, and core products.
3. **🧠 Analysis Agent:** Synthesizes the raw data from the first two agents into a strict JSON payload, calculating a 0-100 buying intent score.
4. **✉️ Email Agent:** Drafts a highly personalized, natural-sounding outreach email grounded *only* in the verified analysis.

## 📋 Prerequisites

To run this pipeline, you will need two API keys:
- **[OpenRouter API Key](https://openrouter.ai/)** (For LLM Inference)
- **[Tavily API Key](https://tavily.com/)** (For Web Search capabilities)

## 🛠️ Installation

1. **Clone the repository**
   ```bash
   git clone [https://github.com/yourusername/multi-agent-sales-pipeline.git](https://github.com/yourusername/multi-agent-sales-pipeline.git)
   cd multi-agent-sales-pipeline



2. **Install the required dependencies**
```bash
pip install strands-agents strands-agents-tools tavily-python openai pydantic gradio



3. **Configure your API keys**
Open `app.py` and replace the placeholder strings with your actual keys, or set them in your environment variables.
```python
openrouter_key = "sk-or-v1-..."
tavily_key = "tvly-..."

```



## 🚀 Quick Start (Running the UI)

This project includes a built-in Gradio 6.0 web interface to visualize the agent workflow and inspect the intermediate reasoning.

Run the application:

```bash
python app.py

```

The terminal will output a local URL (typically `http://127.0.0.1:7860`). Open this in your browser to interact with the pipeline.

## 🧠 Model Configuration

By default, the pipeline uses `anthropic/claude-3.7-sonnet` via OpenRouter for high-quality writing and reasoning. Because the agents use standard OpenAI client configurations, you can easily swap models by changing the `model_id` in the code:

* **High Quality:** `anthropic/claude-3.7-sonnet`
* **Fast & Cheap:** `deepseek/deepseek-chat-v3`
* **Large Context:** `google/gemini-2.5-pro`

## 🤝 Contributing

Contributions, issues, and feature requests are welcome! Feel free to check the [issues page](https://www.google.com/search?q=https://github.com/yourusername/multi-agent-sales-pipeline/issues) if you want to contribute.
