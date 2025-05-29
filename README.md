/market_brief_agent
├── /data_ingestion       # API and scraping agents
│   ├── market_api.py     # Yahoo/AlphaVantage polling
│   └── filings_scraper.py# SEC/SEDAR scraping or simpler source
├── /agents
│   ├── retriever_agent.py# FAISS/Pinecone top-k embedding search
│   ├── analysis_agent.py # Earnings surprise / risk delta calculation
│   └── language_agent.py # LLM synthesis via LangChain
├── /orchestrator
│   └── router.py         # FastAPI router for STT → LLM → TTS flow
├── /streamlit_app
│   └── app.py            # Simple dashboard & voice/text I/O UI
├── /voice_agent
│   ├── stt.py            # Whisper (OpenAI or local)
│   └── tts.py            # pyttsx3, ElevenLabs, or similar
├── /docs
│   └── ai_tool_usage.md  # Prompt logs, tool usage, model configs
├── Dockerfile
├── requirements.txt
└── README.md
"Today’s Asia Tech allocation is {{ allocation }}% of AUM, {{ direction }} from {{ previous }}%. 
{{ company1 }} {{ beat/miss }} by {{ surprise }}%. 
Regional sentiment is {{ tone }} due to {{ reason }}."
Voice → STT (Whisper) → FastAPI Orchestrator → Retriever & Analysis → LLM → TTS
