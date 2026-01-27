---
marp: true
theme: default
paginate: true
title: "Wrap-Up: Next Steps & Beyond"
---

# What You Built Today

<!-- TODO: Replace with custom rag-full-pipeline.png (end-to-end architecture).
     See image-prompt-seed.txt for style guide. -->
![center w:900](../opening/img/overall-rag-arch.jpeg)

A complete RAG pipeline — from raw documents to chat interface:

| Module | What you built |
|---|---|
| **Module 1** | Chunked documents, embedded them, stored in ChromaDB |
| **Module 2** | Queried by meaning, retrieved relevant chunks, tuned results |
| **Module 3** | Connected retrieval to an LLM through a chat interface |

<!--
Speaker notes:
- "Let's take a step back and look at what you've done in the last two hours."
- Walk through the diagram one more time, but now they've BUILT each piece
- "You didn't just learn about RAG — you built a working pipeline."
-->

---

# The Key Insight

The LLM has **no connection** to your database.

Your application retrieves context, assembles a prompt, and sends it through the **context window** — the only door.

![center w:800](../mod-3/img/contruction-of-context.jpeg)

<!--
Speaker notes:
- Quick callback to the Module 3 diagram
- "Remember — the LLM doesn't know ChromaDB exists. It just reads what you give it."
- "That simplicity is what makes RAG approachable AND extensible."
-->

---

# This Is Your Starting Point

Everything you built today is a foundation you own and can extend.

The Chat RAG Explorer app is open source:
**github.com/AlteredCraft/chat-rag-explorer**

The workshop materials:
**github.com/AlteredCraft/workshop-rag-basics**

---

# Next Step: Your Own Corpus

Swap in **your documents** — the pipeline doesn't change:

1. Place your markdown files in the corpus directory
2. Run the ingestion script (Module 1)
3. Point the chat app at your new ChromaDB collection (Module 3)

**Think about your use case:**
- Internal documentation?
- Product knowledge base?
- Research papers?
- Customer support articles?

<!--
Speaker notes:
- "What's the first dataset you'd want to try this with?"
- Let people think for a moment — this is where it gets personal
- "The Morn Chronicles was a stand-in. Now think about YOUR data."
-->

---

# Next Step: Tune Your Parameters

Every stage has knobs you can turn:

| Stage | Parameter | Effect |
|---|---|---|
| **Chunking** | Chunk size, overlap | Controls granularity of retrieval |
| **Retrieval** | top-k, distance threshold | Controls how many results and how relevant |
| **Generation** | Temperature, top-p | Controls creativity vs. precision |
| **System Prompt** | Prompt text | Controls how the LLM uses context |

You explored these today — now experiment with your own data.

---

# Next Step: Try Different Models

The pipeline is **model-agnostic** at every stage:

**Embedding models:**
- OpenAI, Cohere, Hugging Face open-source models
- Different models capture different semantic nuances

**LLMs:**
- The Chat RAG Explorer supports any model via OpenRouter
- Try different models on the same query — compare results

**The pipeline stays the same.** Only the model changes.

---

# Your Next Step

You've seen three paths forward:

1. **Your Own Corpus** — swap in your documents, run the same pipeline
2. **Tune Parameters** — adjust chunking, retrieval, and generation settings
3. **Try Different Models** — swap embedding models or LLMs

**Pick one.** What's the first thing you'll try?

<!--
Speaker notes:
- "We've shown you three directions. Now I want you to pick ONE."
- Pause for 10 seconds — let people think
- Quick show of hands: "Who's going to start with their own documents? Tuning parameters? Different models?"
- "Having a concrete next step makes the difference between 'that was cool' and actually using this."
- The syllabus success signal: each person mentally picks one path
-->

---

# Going Further: Advanced Topics

<!-- TODO: Replace with custom rag-advanced-topics.png (pipeline with advanced branches).
     See image-prompt-seed.txt for style guide. -->
![center w:900](../opening/img/overall-rag-arch.jpeg)

Each stage of the pipeline has deeper techniques:

**Ingestion & Embedding:**
- Advanced chunking strategies (semantic, recursive)
- Embedding model fine-tuning

**Retrieval:**
- Rerankers (re-score results for relevance)
- Alternative retrievers (hybrid search, keyword + semantic)
- Metadata filtering

---

# Going Further: Frameworks & Deployment

**Frameworks** that build on these concepts:
- LangChain, LlamaIndex — orchestration layers for RAG pipelines
- These add complexity but also flexibility at scale

**Deployment paths:**
- ChromaDB → managed vector databases (Pinecone, Weaviate, ChromaDB Cloud)
- Local LLM → managed APIs (OpenAI, Anthropic, AWS Bedrock)
- Chat app → deployed web service

**Enterprise:**
- AWS Bedrock, Databricks — RAG as a managed service
- Same concepts, different infrastructure

<!--
Speaker notes:
- "These are all extensions of what you built today — not replacements."
- "The concepts don't change. The infrastructure scales."
- "LangChain and LlamaIndex are popular but add abstraction. Start with what you built today to understand the fundamentals, then add frameworks when you need them."
-->

---

# Parking Lot

Questions we didn't get to today?

Drop them in the chat or raise a hand — we'll capture them for follow-up.

<!--
Speaker notes:
- Capture questions on a shared doc or whiteboard
- These become follow-up resources or future workshop topics
- "We'll share follow-up materials that address these"
-->

---

# Feedback

Your feedback shapes the next iteration of this workshop.

<!-- TODO: Add QR code and link to Google Form — to be added before workshop day.
     Form spec: support-docs/feedback-form.md -->

**[Feedback Form Link]**

<!--
Speaker notes:
- "Please take 2 minutes to fill this out before you leave"
- QR code on screen for easy mobile access
- "Be honest — what worked, what didn't, what would you change?"
-->

---

<!-- _class: lead -->

# Thank You

**Keep building. Swap in your own data. Experiment.**

The pipeline is yours now.

<!--
Speaker notes:
- Thank the other instructors and helpers
- Remind about the GitHub repos
- "We're here for a few minutes after if you have questions"
-->
