<div align="center">
<img src="https://img.shields.io/badge/✈️_Travel_Itinerary_Bot-Local_LLM_Powered-blue?style=for-the-badge&labelColor=1a1a2e&color=16213e" alt="Project Banner" width="600"/>

<br/>

<img src="https://img.shields.io/badge/Gemma_4-Ollama-orange?style=flat-square&logo=google&logoColor=white" alt="Gemma 4"/>
<img src="https://img.shields.io/badge/Python-3.9+-blue?style=flat-square&logo=python&logoColor=white" alt="Python"/>
<img src="https://img.shields.io/badge/Streamlit-Web_UI-red?style=flat-square&logo=streamlit&logoColor=white" alt="Streamlit"/>
<img src="https://img.shields.io/badge/Click-CLI-green?style=flat-square&logo=gnu-bash&logoColor=white" alt="Click CLI"/>
<img src="https://img.shields.io/badge/License-MIT-yellow?style=flat-square" alt="License"/>

<br/><br/>

<strong>Part of <a href="https://github.com/kennedyraju55/90-local-llm-projects">90 Local LLM Projects</a> collection</strong>

</div>

<br/>
# ✈️ Travel Itinerary Bot

![Python](https://img.shields.io/badge/Python-3.10%2B-blue?logo=python)
![LLM](https://img.shields.io/badge/LLM-Gemma%204-orange)
![License](https://img.shields.io/badge/License-MIT-green)
![UI](https://img.shields.io/badge/UI-Streamlit-red?logo=streamlit)

> AI-powered vacation planner that creates detailed day-by-day travel itineraries using a local LLM.

## ✨ Features

- **Global Destinations** — Plan trips to any destination worldwide
- **Multi-Destination Support** — Chain multiple cities in one trip
- **3 Budget Levels** — Budget, moderate, and luxury options with cost estimates
- **Budget Breakdown** — Detailed cost analysis by category with charts
- **Packing List Generator** — Weather & activity-appropriate packing suggestions
- **Interest-Based Planning** — Tailor activities to your interests
- **Day-by-Day Schedule** — Morning, afternoon, and evening activities
- **Place Details** — Get detailed info about any attraction
- **Streamlit Web UI** — Interactive browser-based interface with map placeholder and budget charts
- **Rich CLI Interface** — Beautiful formatted terminal output
- **Configurable** — YAML-based settings

## 📦 Installation

```bash
pip install -r requirements.txt
pip install -e .
```

## 🚀 Usage

### CLI

```bash
# Single destination
python -m travel_planner.cli --destination "Tokyo" --days 5 --budget moderate

# Multi-destination
python -m travel_planner.cli --destination "Tokyo, Kyoto, Osaka" --days 3 --budget luxury

# With interests
python -m travel_planner.cli --destination "Paris" --days 7 --budget luxury --interests "food,art,history"
```

### Web UI (Streamlit)

```bash
streamlit run src/travel_planner/web_ui.py
```

### CLI Commands

| Command       | Action                        |
|---------------|-------------------------------|
| `<place>`     | Get place details             |
| `budget`      | Generate budget breakdown     |
| `pack`        | Generate packing list         |
| `quit`        | Exit the session              |


## 🧪 Running Tests

```bash
pytest tests/ -v
```

## ⚙️ Configuration

Edit `config.yaml` to customize model, travel defaults, and storage paths.

## 📸 Screenshots

<div align="center">
<table>
<tr>
<td><img src="https://via.placeholder.com/400x250/1a1a2e/e94560?text=CLI+Interface" alt="CLI Interface"/></td>
<td><img src="https://via.placeholder.com/400x250/16213e/e94560?text=Web+UI" alt="Web UI"/></td>
</tr>
<tr>
<td align="center"><em>CLI Interface</em></td>
<td align="center"><em>Streamlit Web UI</em></td>
</tr>
</table>
</div>

## 📁 Project Structure

```
05-travel-itinerary-bot/
├── src/
│   └── travel_planner/
│       ├── __init__.py      # Package metadata
│       ├── core.py          # Core business logic
│       ├── cli.py           # Click CLI interface
│       ├── web_ui.py        # Streamlit web interface
│       ├── config.py        # Configuration management
│       └── utils.py         # Budget, packing, multi-dest helpers
├── tests/
│   ├── __init__.py
│   ├── test_core.py         # Core logic tests
│   └── test_cli.py          # CLI tests
├── config.yaml              # Default configuration
├── setup.py                 # Package setup
├── requirements.txt         # Dependencies
├── Makefile                 # Common commands
├── .env.example             # Example environment variables
└── README.md                # This file
```
