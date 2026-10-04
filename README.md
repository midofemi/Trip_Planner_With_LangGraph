# A Multi-Agent Travel Planner with LangGraph

An open-source, AI-powered travel assistant designed to transform a simple trip request into a complete and organized travel plan. Users can describe their travel needs in natural language, and the system generates relevant flight options, hotel recommendations, and a structured daily itinerary.

The application is built around a multi-agent architecture using LangGraph and LangChain, with FastAPI providing the backend API.

## Why this project?

Organizing a trip often requires searching across different platforms for flights, accommodations, activities, and other travel information. This project simplifies that process by bringing those tasks together within a single AI-driven workflow.

The system divides the planning process among specialized agents:

1. Flight Agent – searches for suitable flight options.

2. Hotel Agent – researches accommodations based on the trip requirements.

3. Itinerary Agent – creates a detailed day-by-day travel schedule.

4. Response Agent – combines the results from the other agents into a clear and useful final travel plan.

LangGraph coordinates these agents and manages how information moves through each stage of the travel-planning workflow.

## Project Structure

```text
.
├── app.py                # FastAPI app entry point
├── backend.py            # LangGraph travel workflow
├── requirements.txt      # Python dependencies
├── static/               # Static frontend assets
├── templates/            # HTML templates
└── tools/                # Flight and web search integrations
```

## Prerequisites

Before running the project locally, make sure you have:

- Python 3.10 or newer installed
- PostgreSQL running and accessible
- API keys for:
  - Groq
  - Tavily
  - AviationStack

## Environment Variables

Create a .env file in the project root with the following variables:

```env
DATABASE_URL=postgresql://user:password@localhost:5432/travel_db
GROQ_API_KEY=your_groq_api_key
AVIATIONSTACK_API_KEY=your_aviationstack_api_key
TAVILY_API_KEY=your_tavily_api_key
DEFAULT_ORIGIN_IATA=DAC
```

## Installation

```bash
conda create -p venv python=3.11 -y
conda activate venv/   # On Windows: .venv\Scripts\activate
pip install -r requirements.txt
```

## Running the App

Start the FastAPI server:

```bash
python app.py
```

Then open your browser at:

```text
http://127.0.0.1:8000/
or
localhost:8000/
```


