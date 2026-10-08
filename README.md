# Autonomous-Multi-Agent-r 🤖🏢

> Enterprise-grade Generative AI & Agentic Platform featuring Autonomous Multi-Agent Workflows, Production RAG & Retrieval Systems, Vector Databases, LLM Evaluation Frameworks, and QLoRA Fine-Tuning.

## 📌 Executive Summary
**Autonomous-Multi-Agent-r** is an end-to-end enterprise AI platform designed to architect, benchmark, and deploy production-ready Generative AI systems. It unifies the entire modern enterprise AI lifecycle across 5 production modules:

1. **🤖 Autonomous Multi-Agent Systems:** Cooperative agent networks (Planning, Pricing, Evaluation, Negotiation) equipped with tool-calling capabilities and persistent session memory.
2. **📚 Production RAG & Retrieval Systems:** Knowledge-base ingestion, hybrid semantic retrieval, context re-ranking, and hallucination reduction.
3. **⚡ Vector Databases & Embeddings:** Scalable vector index structures using ChromaDB and high-dimensional semantic search.
4. **📊 Evaluation Frameworks & Observability:** Systematic LLM benchmarking, RAG Triad metrics (Context Relevance, Groundedness, Answer Relevance), and automated evaluation suites.
5. **🧠 Core ML & QLoRA Fine-Tuning:** Parameter-efficient 4-bit (NF4) domain adaptation and Supervised Fine-Tuning (SFT) for specialized model tasks.

---

## 🏛️ Platform Architecture
```text
                       [Enterprise Query / Goal]
                                  │
                                  ▼
                    ┌───────────────────────────┐
                    │  Planning & Agent Engine  │
                    │   (Autonomous Loop & Tool)│
                    └─────────────┬─────────────┘
                                  │
         ┌────────────────────────┼────────────────────────┐
         ▼                        ▼                        ▼
┌─────────────────┐      ┌─────────────────┐      ┌─────────────────┐
│ Vector Database │      │ Advanced RAG &  │      │ QLoRA Fine-Tuned│
│  (ChromaDB)     │      │ Retrieval Engine│      │ Adapter Models  │
└────────┬────────┘      └────────┬────────┘      └────────┬────────┘
         │                        │                        │
         └────────────────────────┼────────────────────────┘
                                  ▼
                   ┌─────────────────────────────┐
                   │   Evaluation & Guardrails   │
                   │ (RAG Triad & Metric Suite)  │
                   └──────────────┬──────────────┘
                                  ▼
                       [Validated Response]
```

---

## 📁 Repository Structure

```text
├── autonomous_agents/                 # Module 1: Autonomous Multi-Agent Workflows
│   ├── agents/                        # Specialized agent definitions (Planning, Deals, Scrapers)
│   ├── deal_agent_framework.py        # Central agent orchestrator & tool execution
│   ├── price_is_right.py              # Autonomous decision logic
│   ├── memory.json                    # Persistent agent memory store
│   └── day1.ipynb - day5.ipynb        # Agent development progression
│
├── rag_retrieval_system/              # Module 2: Enterprise RAG & Retrieval System
│   ├── knowledge-base/                # Domain document ingestion repository
│   ├── implementation/                # Retrieval pipelines & context injection
│   ├── pro_implementation/            # Production RAG pipeline with re-ranking
│   ├── evaluator.py                   # RAG retrieval quality evaluation
│   ├── app.py                         # Interactive RAG service application
│   └── day1.ipynb - day5.ipynb        # RAG architectural progression
│
├── vector_databases/                  # Module 3: Vector Databases & Embeddings
│   ├── system_info.py                 # ChromaDB indexing & vector search engine
│   └── day3.ipynb - day5.ipynb        # High-dimensional embeddings & vector space analysis
│
├── evaluation_frameworks/             # Module 4: LLM & RAG Evaluation Framework
│   ├── pricer/                        # Metric evaluators & ground truth benchmarks
│   ├── util.py                        # Automated evaluation runners & scoring
│   ├── results.ipynb                  # Quantitative benchmark analysis
│   └── day1.ipynb - day5.ipynb        # Evaluation metrics & guardrail labs
│
├── qlora_fine_tuning/                 # Module 5: Core ML & QLoRA Fine-Tuning
│   ├── jsonl/                         # Instruction dataset pairs
│   ├── redemption_train.ipynb         # 4-bit PEFT/TRL supervised fine-tuning loop
│   ├── redemption_run.ipynb           # Model evaluation & generation inference
│   └── day1.ipynb - day5.ipynb        # Quantization & loss convergence labs
│
├── requirements.txt                   # Unified dependencies
└── README.md
```

---

## ⚙️ Setup & Verification

### 1. Installation
```bash
python -m venv venv
# Windows:
.\venv\Scripts\activate
# Linux/macOS:
source venv/bin/activate

pip install -r requirements.txt
```

### 2. Environment Configuration
Create a `.env` file in the project root:
```bash
OPENAI_API_KEY=your_key_here
# Optional local model endpoint:
# OLLAMA_HOST=http://localhost:11434
```

### 3. Running Modules
* **Launch Autonomous Agents:**
  ```bash
  cd autonomous_agents
  python deal_agent_framework.py
  ```
* **Run RAG Application:**
  ```bash
  cd rag_retrieval_system
  python app.py
  ```
* **Run Automated Evaluation Suite:**
  ```bash
  cd evaluation_frameworks
  jupyter lab results.ipynb
  ```

---

## 📄 License
MIT License
