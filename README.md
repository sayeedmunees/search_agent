# 🧠 Simple Google Search Agent (Gemini 2.5 Flash + ADK)

A minimal example of an AI-powered search assistant built using **Gemini 2.5 Flash Lite** and the **Google Agent Development Kit (ADK)**.  
This agent can understand general questions and use **Google Search** to fetch real-time, relevant answers — all running locally with an in-memory runner.

---

## 🚀 Features

- 💬 Answers general questions intelligently  
- 🌐 Uses **Google Search** for up-to-date information  
- ⚙️ Built with **Gemini 2.5 Flash Lite** and **ADK**  
- 🧩 Runs entirely in memory using `InMemoryRunner`  
- 🪶 Simple, lightweight, and easy to extend  

---

## 📦 Installation

Make sure you have Python 3.9+ installed.

```bash
# Clone this repository
git clone https://github.com/yourusername/simple-search-agent.git
cd simple-search-agent

# (Optional) Create and activate a virtual environment
python -m venv venv
source venv/bin/activate  # On Windows use `venv\Scripts\activate`

# Install the Google ADK and related packages
pip install google-adk google-genai
```

---

## 🧩 Example Code

```python
from google.adk.agents import Agent
from google.adk.runners import InMemoryRunner
from google.adk.tools import google_search
from google.genai import types

print("✅ ADK components imported successfully.")

root_agent = Agent(
    name="helpful_assistant",
    model="gemini-2.5-flash-lite",
    description="A simple agent that can answer general questions.",
    instruction="You are a helpful assistant. Use Google Search for current info or if unsure.",
    tools=[google_search],
)

print("✅ Root Agent defined.")

runner = InMemoryRunner(agent=root_agent)

print("✅ Runner created.")
```

---

## ▶️ Usage

Once the runner is set up, you can run interactive prompts or trigger queries directly in your Python environment:

```python
response = runner.run("Who won the 2025 NBA Finals?")
print(response.text)
```

The agent will use **Google Search** when necessary to retrieve accurate, current information.

---

## 🧱 Project Structure

```
simple-search-agent/
│
├── main.py          # Example agent definition and runner
├── README.md        # You’re here
└── requirements.txt # Dependencies (optional)
```

---

## 🔧 Customization

You can modify:
- The `instruction` field to change the agent’s tone or behavior  
- The `tools` list to add new capabilities  
- The `model` to use other Gemini variants (e.g., `gemini-2.5-pro`)  

---

## 📄 License

This project is licensed under the **MIT License** — feel free to use, modify, and share.
