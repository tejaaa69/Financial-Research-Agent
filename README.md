# 🏦 Financial Research Agent with Hybrid RAG

A multi-tool AI agent for financial analysis combining:
- **Hybrid RAG** (Vector + BM25 + Reranker + HyDE) for PDF documents
- **Macro Factor Correlation Engine** (7 economic indicators for Gold)
- **Real-time APIs** (FRED, Alpha Vantage, Tavily Search)
- **LangGraph Agent** with tool-calling and memory

## 🚀 Quick Start

### 1. Get API Keys (all free):
- [HuggingFace](https://huggingface.co/settings/tokens) - Free
- [LlamaCloud](https://cloud.llamaindex.ai) - 1000 free pages
- [Groq](https://console.groq.com) - Free tier
- [Tavily](https://tavily.com) - 1000 free searches
- [FRED](https://fred.stlouisfed.org) - Free
- [Alpha Vantage](https://alphavantage.co) - Free
- [Ngrok](https://ngrok.com) - Free

### 2. Run in Google Colab:
Open `01_rag_setup.ipynb` → Run all cells → Save to Drive
Open `02_agent_setup.ipynb` → Run all cells → Ask queries

### 3. Example Query:

"What is the current federal funds rate and how does it impact gold prices?"


## 📊 Sample Output

──────────────────────────────────────────────────────
► PART 2: SIGNAL SCORECARD  (deterministic, no LLM)
  DFII10       LEVEL    1.91       z=+1.18  → BEARISH    [-2]  ██░
  FEDFUNDS     LEVEL    3.64       z=+0.67  → BEARISH    [-1]  █░░
  HOUST        MOM_PCT  10.767     z=+1.40  → BEARISH    [-1]  █░░

  NET SCORE: -3.279  |  DATA CONFIDENCE: 50%  |  SIGNALS: 3/6

──────────────────────────────────────────────────────
► PART 3: AI RATIONALE  (synthesis only)
The current federal funds rate is 3.64, which is contributing to a bearish verdict. Housing construction starts have increased by 10.77% month-over-month, but this growth is likely to be hindered by the rising interest rates. The price of Gold (GLD) has fallen to $414.71, a 13% decline since the conflict in the Middle East began, as escalating tensions have heightened inflation concerns and driven energy prices sharply higher. The DFII10 rate is at 1.91, which is also contributing to the bearish verdict, with a z-score of +1.18.

──────────────────────────────────────────────────────
► FINAL VERDICT:  BEARISH

► TRIGGER CONDITION:
  WATCH [DFII10 LEVEL]: Currently 1.91 (z=+1.18, bearish). A reversal toward historical mean (0.48) would add ~1.8 to net score. Expected lag: ~1 weeks.
══════════════════════════════════════════════════════



## 🛠️ Tech Stack

| Component | Technology |
|-----------|------------|
| LLM | Llama-3.3-70B (Groq) + Llama-2-7B (local) |
| RAG | LlamaIndex + ChromaDB |
| Agent | LangGraph |
| Embeddings | BAAI/bge-small-en-v1.5 |
| Parsing | LlamaParse |

## 📂 Notebooks

- `01_rag_setup.ipynb` - Build RAG pipeline, parse PDFs, create vector store
- `02_agent_setup.ipynb` - LangGraph agent with tools + correlation engine

## 📧 Contact

[Tejas S Patil] - [tejaspatil200354@gmail.com]
