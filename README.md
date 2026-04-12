# ✈️ Travel Itinerary Bot

![Python 3.11+](https://img.shields.io/badge/Python-3.11%2B-3776AB?logo=python&logoColor=white)
![License MIT](https://img.shields.io/badge/License-MIT-green.svg)
![Local LLM](https://img.shields.io/badge/LLM-Gemma%204-FF6F00?logo=google&logoColor=white)
![Privacy First](https://img.shields.io/badge/Privacy-First-blueviolet?logo=lock&logoColor=white)
![Ollama](https://img.shields.io/badge/Ollama-Powered-black?logo=ollama&logoColor=white)

**AI-powered vacation planner that builds day-by-day itineraries with activities, restaurants, costs, and packing lists — running 100% locally with Gemma 4.**

```
+---------------------------------------------------------+
|                TRAVEL ITINERARY BOT                     |
|                                                         |
|  +----------+    +---------------+    +--------------+  |
|  | Traveler  |--->|  CLI / Web UI |--->|  Planner     |  |
|  | Input     |<---|  (Rich /      |<---|  Core        |  |
|  | (dest,    |    |  Streamlit)   |    +------+-------+  |
|  |  days,    |    +---------------+           |          |
|  |  budget)  |                                v          |
|  +----------+    +---------------+    +--------------+  |
|                  | Budget        |<-->|  Ollama API  |  |
|  +----------+    | Breakdown &   |    |  (Gemma 4)   |  |
|  | Saved     |<--| Packing List  |    |  :11434      |  |
|  | Itiner.   |   | Generator     |    +--------------+  |
|  | (JSON)    |   +---------------+                      |
|  +----------+          |                                |
|                  +-----v--------+                       |
|                  | Multi-Dest.  |                       |
|                  | Planner      |                       |
|                  | (A -> B -> C)|                       |
|                  +--------------+                       |
+---------------------------------------------------------+
```

## Features

- **Day-by-Day Itineraries** — Morning, afternoon, and evening activities with time estimates and logistics
- **Multi-Destination Trips** — Chain multiple cities into a single itinerary with transit planning
- **3 Budget Tiers** — Budget, moderate, and luxury options with estimated costs per activity
- **Restaurant Picks** — Local food recommendations for every meal slot
- **Place Details** — Drill into any attraction for hours, fees, tips, and nearby sights
- **Budget Breakdown** — Detailed cost estimate covering accommodation, food, transport, and activities
- **Packing List Generator** — Weather-appropriate packing lists tailored to your destination and interests
- **Save & Compare** — Store itineraries locally as JSON for future reference
- **Web UI + CLI** — Streamlit dashboard for visual planning or Rich terminal for quick generation
- **100% Local & Private** — Your travel plans never leave your machine; no cloud APIs

## Quick Start

### Prerequisites

| Requirement | Version |
|-------------|---------|
| Python      | 3.11+   |
| Ollama      | latest  |
| Gemma 4     | via Ollama |

### Install & Run

```bash
# 1. Clone the repository
git clone https://github.com/kennedyraju55/travel-itinerary-bot.git
cd travel-itinerary-bot

# 2. Install dependencies
pip install -r requirements.txt

# 3. Start Ollama and pull Gemma 4
ollama serve &
ollama pull gemma4

# 4a. Launch the Web UI
streamlit run src/travel_planner/web_ui.py

# 4b. Or use the CLI
python -m travel_planner.cli plan --destination "Tokyo" --days 5 --budget moderate
```

### Docker

```bash
docker-compose up
# Web UI at http://localhost:8501
```

## Tech Stack

| Layer        | Technology                          |
|-------------|--------------------------------------|
| LLM          | Gemma 4 via Ollama                  |
| Backend      | Python 3.11, Click CLI              |
| Web UI       | Streamlit                           |
| API          | FastAPI / Uvicorn                   |
| Terminal UI  | Rich (panels, tables, progress)     |
| Config       | PyYAML                              |
| Data         | pandas                              |
| Testing      | pytest                              |
| Containers   | Docker, Docker Compose              |

## Project Structure

```
travel-itinerary-bot/
├── src/travel_planner/
│   ├── core.py         # Itinerary, budget, packing list logic
│   ├── cli.py          # Click CLI with Rich output
│   ├── web_ui.py       # Streamlit web dashboard
│   ├── api.py          # FastAPI REST endpoints
│   ├── config.py       # YAML configuration loader
│   └── utils.py        # LLM client helpers & utilities
├── common/
│   └── llm_client.py   # Shared Ollama/Gemma 4 client
├── tests/
│   ├── test_core.py    # Unit tests for core logic
│   └── test_cli.py     # CLI integration tests
├── config.yaml         # Travel defaults, model settings
├── requirements.txt    # Python dependencies
├── Dockerfile          # Multi-stage Docker build
├── docker-compose.yml  # Full stack with Ollama
├── Makefile            # Dev shortcuts (install, test, run)
└── setup.py            # Package setup with entry points
```

## Author

**Nrk Raju Guthikonda**
Senior Software Engineer @ Microsoft — Copilot Search Infrastructure

- GitHub: [kennedyraju55](https://github.com/kennedyraju55)
- Dev.to: [kennedyraju55](https://dev.to/kennedyraju55)
- LinkedIn: [nrk-raju-guthikonda](https://linkedin.com/in/nrk-raju-guthikonda-504066a8/)

---

<p align="center">Built with Gemma 4 — part of a 90+ local LLM project portfolio</p>
