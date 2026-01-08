# Build Your Own AI-Powered Document Search

## What you'll learn

- Understand why RAG exists and how it solves LLM hallucination and knowledge problems by grounding responses in your own documents.
- Build a complete ingestion pipeline that chunks documents, generates embeddings, and stores vectors in ChromaDB.
- Query your vector database using similarity search and interpret results with tuning parameters like top-k and thresholds.
- Connect retrieval to a web chat interface, completing the full RAG loop from question to grounded answer.


## About this course

Large language models (LLMs) are powerful, but they hallucinate, confidently generating plausible-sounding information that isn't true. They also can't access your private documents, internal knowledge bases, or recent information outside their training data.

Retrieval-Augmented Generation (RAG) solves this by giving LLMs a "context window steering lever." Instead of relying solely on trained knowledge, RAG retrieves relevant chunks from your own corpus and feeds them to the model at query time, grounding responses in actual source material.

In this hands-on workshop, you'll build a working RAG system from scratch. You'll ingest documents, generate embeddings, store them in a vector database, write similarity queries, and wire everything into a chat interface. By the end, you'll have a functional AI-powered document search running locally—and understand every piece of the pipeline.

**In detail, you'll:**

- Set up your environment and verify all dependencies using the provided setup script.
- Load markdown documents, extract metadata (title, author, date), and chunk text with configurable overlap strategies.
- Generate vector embeddings and store them in ChromaDB collections.
- Encode queries and perform similarity search, interpreting scores and tuning retrieval parameters.
- Launch a web-based Python chat app that completes the full RAG loop: query → retrieve → generate → display.
- Inspect and edit system prompts to understand how retrieval and generation work together.
- Diagnose common failures by distinguishing retrieval problems from generation problems.


## Who should join?

Those who want hands-on experience building RAG systems. Basic familiarity with programming and working from the command line is recommended.  Python is used for all coding exercises so some familiarity is helpful but the code in use will be minimal (focus is on the RAG workflow).

**Bring your own laptop**: For this delivery we will not be able to provide computers to complete the exercises. Bring your MacOS or Windows laptop. 


## Pre-Work

Complete the following 24 hours before the workshop (details provided upon registration):

- Clone the workshop repository from GitHub
- Run the environment verification script (`verify_setup.sh` or `verify_setup.ps1`)
- Set up API credentials (free-tier options available)


## Course Outline

- **Opening**

  Welcome, environment verification, RAG conceptual primer, hallucination demo, RAG loop diagram walkthrough

- **Module 1: Ingest & Embed**

  Corpus structure walkthrough, loading documents, extracting metadata, chunking strategies with overlap, embedding generation, storing in ChromaDB

- **Module 2: Query & Retrieve**

  Embedding space visualization, similarity search concepts, query encoding, ChromaDB query API, interpreting similarity scores, tuning parameters (top-k, thresholds, filters), introduction to reranking

- **Module 3: Connect to Chat**

  Python chat app architecture, API key setup, running the chat app, full RAG loop in action, system prompt inspection and editing, debugging retrieval vs. generation failures

- **Wrap-Up**

  RAG architecture recap, next steps (custom corpus, parameter tuning, alternative models), deployment paths, advanced topics overview

## Questions?
[Email the Course Team](mailto:info+rag-course@alteredcraft.com)

## Instructors

- [Daniel Dimick](https://www.linkedin.com/in/dpdimick)
- [Mark Joseph Wallaert](https://www.linkedin.com/in/markwallaert)
- [Sam Keen](https://www.linkedin.com/in/samkeen)
