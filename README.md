cd ~/adkui
cat <<'EOF' > README.md
# 🤖 ADK Agent — Code Vipassana S14E1

> Built and deployed during **Code Vipassana Season 14, Session 1** — a live, instructor-led, production-grade AI engineering session by Google.

## 🌐 Live Demo
👉 [https://agent1service-1057982547244.us-central1.run.app](https://agent1service-1057982547244.us-central1.run.app)

## 📌 About
This project demonstrates building and deploying production-grade AI agents using **Google's Agent Development Kit (ADK) Visual Builder** with **Gemini 2.5 Flash** on **Google Cloud Run**.

## 🚀 Features
- ✅ LLM-powered agent via ADK Visual Builder (low-code, YAML-based)
- ✅ Google Search integration for real-time Retrieval-Augmented Generation (RAG)
- ✅ Multi-agent architecture (root orchestrator + sub-agent)
- ✅ Custom async Python Function Tool with Vertex AI Imagen 3.0
- ✅ Deterministic workflow pipelines (SequentialAgent & LoopAgent)
- ✅ Deployed to Google Cloud Run via `adk deploy cloud_run`

## 🛠️ Tech Stack
| Technology | Purpose |
|---|---|
| Google ADK | Agent framework |
| Gemini 2.5 Flash | LLM model |
| Vertex AI | AI platform |
| Imagen 3.0 | Image generation |
| Cloud Run | Production deployment |
| Python | Custom tools |
| YAML | Agent configuration |

## 📁 Project Structure
```
adkui/
├── Agent0/          # Base agent
├── Agent1/          # Agent with Google Search tool
│   └── root_agent.yaml
├── deploycloudrun.py
└── .gitignore
```

## ⚙️ Setup & Run Locally
```bash
# Clone the repo
git clone https://github.com/vamshiiyer/adk-agent-codevipassana.git
cd adk-agent-codevipassana

# Create virtual environment
pip install uv
uv venv
source .venv/bin/activate

# Install dependencies
uv pip install google-adk==1.22.1 python-dotenv

# Create .env file
cat <<ENV > .env
GOOGLE_GENAI_USE_VERTEXAI=1
GOOGLE_CLOUD_PROJECT=your-project-id
GOOGLE_CLOUD_LOCATION=us-central1
IMAGEN_MODEL=imagen-3.0-generate-002
GENAI_MODEL=gemini-2.5-flash
ENV

# Run locally
adk web
```

## ☁️ Deploy to Cloud Run
```bash
python3 deploycloudrun.py
```

## 🙏 Credits
Built during **[Code Vipassana](https://codevipassana.dev) Season 14, Session 1**

Speakers:
- [Haren Bhandari](https://www.linkedin.com/in/haren-bhandari-abb09924)
- [Abirami Sukumaran](https://www.linkedin.com/in/abiramisukumaran)

## 📄 License
MIT License — see [LICENSE](LICENSE) file for details.
EOF
