# CV–Job Matcher

> AI-powered platform that matches job seekers to relevant job opportunities using semantic search, vector embeddings, and RAG architecture.

---

## 🎯 The Problem

Job seekers spend hours scrolling through hundreds of job postings, most of which are irrelevant. Traditional job boards rely on exact keyword matching — a "Backend Developer" never surfaces for a "Python Engineer" posting, even when the skills are identical.

## 💡 The Solution

CV–Job Matcher uses **semantic AI** to understand the *meaning* behind a candidate's experience and match it against live job postings. Upload your CV once, get a ranked list of jobs that actually fit you — with AI-generated explanations and a skill-gap analysis for each match.

---

## ✨ Features

- 📄 **Smart CV Parser** — extracts skills, experience, and education from any PDF résumé
- 🌐 **Live Job Aggregator** — continuously pulls fresh postings from external APIs
- 🧠 **Semantic Matching Engine** — RAG-based retrieval using vector embeddings
- 💬 **AI Insights** — explains *why* each job is a match in natural language
- 📊 **Skill-Gap Analysis** — tells you exactly which skills to develop
- 🚀 **Direct Apply Links** — one click to the original posting

---

## 🏗️ Architecture
┌─────────────┐
│   CV (PDF)  │
└──────┬──────┘
│
▼
┌──────────────┐     ┌──────────────┐
│  PDF Parser  │ ──▶ │ Gemini LLM   │ ──▶ Structured JSON
└──────────────┘     └──────────────┘
│
▼
┌──────────────┐
│  Embeddings  │
└──────┬───────┘
│
▼
┌──────────────────┐
│   Vector Search  │  ◀── Job Vectors
│      (RAG)       │       (from APIs)
└────────┬─────────┘
│
▼
┌──────────────────┐
│   Gemini LLM     │ ──▶ Ranked Matches
│  + Skill Gaps    │       + Explanations
└──────────────────┘

---

## 🛠️ Tech Stack

| Layer | Technology |
|-------|------------|
| **Backend** | FastAPI (Python) |
| **AI / LLM** | Google Gemini |
| **Embeddings** | Gemini `text-embedding-004` |
| **Vector DB** | ChromaDB |
| **PDF Parsing** | PyMuPDF, pdfplumber |
| **Job Data** | JSearch API (RapidAPI) |
| **Frontend** | React.js + Tailwind CSS |
| **Orchestration** | LangChain |

---

## 📁 Project Structure
cv-job-matcher/
├── backend/
│   ├── app/
│   │   ├── api/          # FastAPI routes
│   │   ├── core/         # Config, settings
│   │   ├── services/     # Business logic (parser, embedder, matcher)
│   │   ├── models/       # Pydantic schemas
│   │   └── main.py
│   ├── tests/
│   └── requirements.txt
├── frontend/             # React app
├── docs/
└── README.md

---

## 🚀 Getting Started

### Prerequisites

- Python 3.11+
- Node.js 18+
- A Google Gemini API key
- A RapidAPI key (for JSearch)

### Backend Setup

```bash
cd backend
python -m venv venv
source venv/bin/activate   # Windows: venv\Scripts\activate
pip install -r requirements.txt

cp .env.example .env
# Add your API keys to .env

uvicorn app.main:app --reload
```

### Frontend Setup

```bash
cd frontend
npm install
npm run dev
```

---

## 📍 Roadmap

- [x] Project setup
- [ ] CV parsing pipeline
- [ ] Job ingestion pipeline
- [ ] Vector embedding & storage
- [ ] RAG matching engine
- [ ] LLM insights & skill-gap analysis
- [ ] React frontend
- [ ] Evaluation & testing
- [ ] Deployment

---




---

## 📬 Contact

For questions or collaboration: open an issue on this repo.
