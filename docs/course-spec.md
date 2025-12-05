# Intro to RAG Workshop — Course Design Specification

## Overview

**Course Title**: "Intro to RAG: Build Your Own AI-Powered Document Search"

**Tagline**: From markdown files to conversational search in 2 hours

**Format**: 2-hour hands-on workshop with self-paced pre-work

**Delivery Context**: Public "Come Build With AI" workshop, 5-10 participants, hosted by metro innovation hub in partnership with local tech meetups

**Target Audience**: Any level of developer who is comfortable Pre-Work Materials. Those who are RAG-curious—comfortable with Python, but haven't built a RAG system before

---

## Learning Objectives

By the end of this workshop, participants will be able to:
1. Explain what RAG is and the problems it solves (covered in pre-work)
2. Ingest documents into a ChromaDB vector database with appropriate chunking
3. Query the vector database and understand how similarity search works
4. Connect their RAG backend to a chat interface for conversational document search
5. Identify next steps for extending their RAG (different embedders, cloud deployment, metadata filtering)

**What Participants Walk Away With**:
- A working local RAG system they built themselves
- A Streamlit chat interface connected to their RAG
- Understanding of the core RAG loop (ingest → embed → retrieve → generate)
- A codebase they can extend with their own documents
- Conceptual foundation to evaluate RAG tools and frameworks

---

## Design Rationale

| Decision | Rationale |
|----------|-----------|
| 2-hour format | First course—walk before run; fits available event slot |
| Hybrid (pre-work + live) | Maximizes hands-on time; pre-work serves as marketing funnel |
| Python prerequisite | No time to teach Python in 2 hours; keeps focus on RAG |
| Hands-on, code-along | In-person events need active participation for engagement |
| Sample corpus with swap option | Ensures consistent troubleshooting; allows personalization |
| Streamlit for Chat UI | Visual "wow factor" for finale; minimal setup friction |
| Checkpoint solutions | Nobody gets left behind; everyone experiences the finale |
| Free-tier LLM API (Gemini/Groq) | No credit card barrier for public workshop participants |
| Ollama local demo | Addresses data privacy concerns; shows architectural flexibility |
| Corpus validation script | Catches format issues before they derail hands-on portion |

---

## Pre-Work Materials

**Purpose**: Ensure participants arrive with a working environment and baseline understanding.

**Part A: Environment Setup (Required)**
- Install Python 3.11+
- Install UV package manager
- Clone the workshop repository
- Run verification script (`verify_setup.py`)
- Run corpus validation script (`check_corpus.py`) against sample corpus
- Troubleshooting guide for common issues

**Part B: Conceptual Foundation (10-15 minute read)**
- The problem: "You have documents. You want to ask questions about them."
- What RAG does at a high level (no implementation details)
- Why vector embeddings matter (conceptual)
- Preview of what we'll build (screenshot of final Streamlit chat)
- Privacy note: Workshop uses cloud APIs by default; we'll demo a fully local option (Ollama)

**Part C: Optional Preparation**
- Link to blog post for deeper context
- Instructions for preparing own corpus + running `check_corpus.py` to validate
- Ollama installation for local-only participants

**Delivery**: Markdown file in workshop repo, sent to registrants upon signup.

---

## Live Session Structure

### Opening (10 minutes)
- Welcome, introductions, environment check
- Helper assists stragglers with setup
- Brief recap of pre-work concepts
- Demo the end state (finished Streamlit chat)

### Module 1: Ingest & Embed (35 minutes)
- Walkthrough of sample corpus structure
- Live code-along: ingestion script
  - Load markdown files
  - Extract content and metadata (frontmatter)
  - Chunk content (fixed-size with overlap)
  - Create embeddings and store in ChromaDB
- Run ingest against sample corpus
- **Checkpoint**: "Ingestion complete! X chunks created"
- Introduce ChromaDB CLI browser

### Module 2: Query & Retrieve (30 minutes)
- Explain similarity search (whiteboard/slide moment)
- Live code-along: query function
  - Encode question as embedding
  - Search ChromaDB for similar chunks
  - Return top results with metadata
- Interactive exercise: participants write queries
- Discuss results and introduce metadata filtering

### Module 3: Generate Responses (15 minutes)
- Connect retrieval to LLM
- **Default API**: Google Gemini or Groq (free tier, no credit card)
- Live code-along: RAG loop (retrieve → prompt → generate)
- Test with questions
- **Demo Ollama local option**
- **Checkpoint solution distributed**

### Module 4: Connect to Streamlit Chat (15 minutes)
- Brief code tour of pre-built Streamlit app
- Live code-along: wire up RAG backend
- Run app: `streamlit run app.py`
- **Moment of delight**: Chat with your own documents

### Exploration & Customization (5 minutes)
- Ask different questions
- Swap in own corpus
- Experiment with retrieved chunk count

### Wrap-Up (5 minutes)
- Recap: ingest → embed → retrieve → generate → chat UI
- Where to go next (embedding models, ChromaDB cloud, chunking strategies)
- Resources and Q&A
- Feedback collection

---

## Materials & Deliverables

### 1. Workshop Repository (GitHub)
- `verify_setup.py` — pre-work environment verification
- `check_corpus.py` — corpus format validation
- Sample corpus (curated markdown files with frontmatter)
- Starter code with TODOs for live coding
- Checkpoint solutions (tagged branches)
- Complete working solution
- Pre-built Streamlit chat app
- `.env.example` with API key placeholders
- README with setup instructions

### 2. Pre-Work Document
- Environment setup guide
- Corpus validation instructions
- Conceptual primer
- API key setup (Gemini/Groq free tier)
- Optional: Ollama installation, bring-your-own-corpus instructions

### 3. Slide Deck (Minimal)
- Title / agenda
- "What is RAG" diagram
- Similarity search visualization
- Architecture diagram
- "Where to go next" resources
- Feedback form link

### 4. Instructor Notes
- Timing guide per section
- Common troubleshooting issues
- Talking points for transitions
- Discussion prompts

### 5. Helper Briefing Doc
- Workshop overview
- Common failure points and fixes
- Checkpoint solution locations
- Escalation path

---

## Research Links

- [ChromaDB Documentation](https://docs.trychroma.com/docs/overview/introduction) — primary vector database used in workshop
- [ChromaDB CLI Tools](https://docs.trychroma.com/docs/cli/install) — for collection browsing demo
- [Weaviate Chunking Strategies Guide](https://weaviate.io/blog/chunking-strategies-for-rag) — reference for chunking concepts
- [Google Gemini API Free Tier](https://ai.google.dev/pricing) — no credit card LLM option
- [Groq API](https://console.groq.com/) — alternative no credit card LLM option
- [Ollama](https://ollama.ai/) — local LLM for privacy-conscious participants
- [Streamlit Documentation](https://docs.streamlit.io/) — chat UI framework

---

## Source Material

This course design is adapted from: [[AlteredCraft/Altered Craft Publications/LongFormWriting/Posts in process or complete/Local RAG/post content|Two Years of Writing, One Afternoon of Code]]