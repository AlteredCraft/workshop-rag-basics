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
3. Query the vector database and understand how similarity search works (just in Python))
4. Connect their RAG backend to a chat interface (LLM) for conversational document search
5. Identify next steps for extending their RAG (different embedders, cloud deployment, metadata filtering)

**What Participants Walk Away With**:
- A working local RAG system they built themselves
- A chat interface connected to their RAG
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
- Install UV package manager
- Use UV to install python if needed.
- Clone the workshop repository
- Run verification script (`verify_setup.py`)
- [TODO, maybe not, rather supply the docs to use] Run corpus validation script (`check_corpus.py`) against sample corpus
- Troubleshooting guide for common issues

---

## Live Session Structure

General notes
- Modules lead with recap , end with teaser to next module
- encourge "if yours is working look to help others"

### Opening (20 minutes)
{{ 
High level overview, here is how the R, A, G work together 
might expand the timeframe to 30??
hint at 'context rot' (chromadb paper)
- improve the coverage of the key concepts here, keep it tight, just enough to orient the learner
}}

- Welcome, introductions, environment check
- Helper assists stragglers with setup
- Brief recap of pre-work concepts
- Demo An anti-example of chatgpt hallucinating on questions regarding our data.
- Notes:
    - Use accessible metaphors
- which includes env validation checks (verify_setup.py works)


### Module 1: Ingest & Embed (35 minutes)
{{ keep the corpus txt }}
- Walkthrough of sample corpus structure
- Live code-along: ingestion script
  - Load markdown files (callout a similar (any doc format, (example: PDF) workflow)
  - Extract content and metadata (frontmatter)
  - Chunk content (fixed-size with overlap)
  - Create embeddings and store in ChromaDB {{ create-or-use }}
- Run ingest against sample corpus
- **Checkpoint**: "Ingestion complete! X chunks created"
- [if time] Introduce ChromaDB CLI browser

## 5 min (minimum) break

### Module 2: Query & Retrieve (30 minutes)
- Explain similarity search (whiteboard/slide moment)
- Sililar to SQL, if they have expereince
- Live code-along: query function
  - Encode question as embedding
  - Search ChromaDB for similar chunks
  - Return top results with metadata (set limit)
  - RAG params: top k , similarity score, etc.
- Interactive exercise: participants write queries
- Discuss results and introduce metadata filtering
- Hint at _Reranker_ to inform them there are approached to overome the challenges here.

### Module 3: Connect to Chat (20 minutes)
- NOTE: This will leverage their API key,
  - Google Gemini (free tier, no credit card, caveot: Google needs to know who you are)
  - Support a few more, Anthropic, OpenAI
- Demo running, and have them run app
  - address any run issues, if extensive, have them buddy up. 
- Test with questions
    - have them repeat the side by compaison
    - ask a question out of context (the resp depends on the LLM itself, but also the steering in the system promt.)
- Show example of the the entire prompt going the the LLM.
- Q&A : best placed here as they have just finished. adapt wrapup as needed. This keeps it more workshop, less lecture.


### Wrap-Up (8 minutes)
- Recap: ingest → embed → retrieve → generate → chat UI
- Where to go next (with the cose base they have) (embedding models, ChromaDB cloud, chunking strategies)
- Overall , where to go next (Enterprise solutions (bedrock, data bricks, etc) (will be in repo, just call it out)
- If time, look to live parking lot
- Collect Feedback for follow up (survey ?)

### Key Take-aways
- Understanding of the need for RAG
  - LM weights are locked (and what that means)
  - Clear on the concept of the Context window (only mechanism to streer the LLM), limits, mention of Context Rot 
- Clear Next steps options
  - Swap in own corpus
  - chunking options
  - Extending the code they have, Chroma Cloud,Supabase, A "cloud" offering (AWS, GCP, Azure)
  - No code options, Notebook LM
  
---

## Materials & Deliverables

### 1. Workshop Repository (GitHub)
- `verify_setup.py` — pre-work environment verification
- Sample corpus (curated markdown files with frontmatter)
- ~~Starter code with TODOs for live coding~~
- ~~Checkpoint solutions (tagged branches)~~
- Complete working solution
- Pre-built chat app (Python, HTML, vanilla JS)
- `.env.example` with API key placeholders
- README with setup instructions

### 2. Pre-Work Document
- Environment setup guide (UV and run `verify_setup.py`)
- ~~Corpus validation instructions~~
- Course overveiw ~~Conceptual primer~~
- API key setup (existing or recomend Gemini free tier)
- ~~Optional: Ollama installation, bring-your-own-corpus instructions~~

### 3. Slide Deck (Minimal, more workshop less lecture)
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

## Notes to integrate
- Have a live parking lot (collect topics , keep the course moving
- [embrace transparency, learning tool] Have a {debug window for the Chat client} + add the "generate memaid diagram" + RAG params: top k , similarity score, etc.
- Add token count and cost
- Keep it dump, make a "RAG" call on each request.
- Mitigate folks getting stuck, have completion starting point.
- Settle on LLM access provider, needs to be free, no cc needed.
- Final big picture of the entire system, calling out the "tuning" opertunities for that system.
- As a fallback, create a OpenRouter api key (0$) cap.

## Research Links

[TODO: Add more, better links]

- [ChromaDB Documentation](https://docs.trychroma.com/docs/overview/introduction) — primary vector database used in workshop
- [ChromaDB CLI Tools](https://docs.trychroma.com/docs/cli/install) — for collection browsing demo
- [Weaviate Chunking Strategies Guide](https://weaviate.io/blog/chunking-strategies-for-rag) — reference for chunking concepts
- [Google Gemini API Free Tier](https://ai.google.dev/pricing) — no credit card LLM option
- [Groq API](https://console.groq.com/) — alternative no credit card LLM option
- [Ollama](https://ollama.ai/) — local LLM for privacy-conscious participants
- [Streamlit Documentation](https://docs.streamlit.io/) — chat UI framework

