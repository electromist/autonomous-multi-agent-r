# Autonomous-Multi-Agent-r 🤖🌐

> Production-grade Autonomous Multi-Agent Collaborative System with Tool Calling, ChromaDB Vector Memory, and QLoRA Domain-Specific LLM Fine-Tuning.

## 📌 Overview
**Autonomous-Multi-Agent-r** represents the cutting-edge frontier of AI Engineering. It combines two foundational pillars:
1. **Autonomous Multi-Agent Orchestration:** Specialized agents (Planning Agent, Scraper/Pricing Agent, Opportunity Evaluator) collaborating to solve complex commercial tasks (discovering bargains, evaluating value arbitrage, persisting memory across sessions).
2. **Core ML / Parameter-Efficient Fine-Tuning (QLoRA):** Adapting open-weights frontier models (Llama 3 / Mistral) using 4-bit NormalFloat (NF4) quantization, LoRA adapter matrices, and supervised fine-tuning (SFT) for high-accuracy domain execution.

## 🧠 System Architecture

### 1. Multi-Agent Collaborative Loop
```text
  User Intent / Market Signal
             │
             ▼
      [Planning Agent]
     (Decomposes Goals)
             │
      ┌──────┴──────────────────┐
      ▼                         ▼
 [Pricing Agent]        [Arbitrage Agent]
(Vector DB Lookup)    (Evaluates Opportunity)
      │                         │
      └──────────┬──────────────┘
                 ▼
     [Persistent ChromaDB & Memory]
```

### 2. QLoRA Domain Fine-Tuning Backbone
- **4-bit NormalFloat (NF4) Quantization:** Drastically reduces VRAM footprint while preserving model weights precision.
- **LoRA Low-Rank Adapters:** Trains low-rank decomposition matrices ($A$ and $B$) on attention projections ($W_q, W_k, W_v, W_o$) without touching frozen base weights.
- **PEFT + TRL Supervised Fine-Tuning:** Custom dataset formatting, cross-entropy loss convergence, and adapter merging.

## 📁 Repository Structure
```text
├── autonomous_agents/                 # Multi-Agent Orchestration Engine
│   ├── agents/                        # Specialized Agent definitions (Planning, Deals, etc.)
│   ├── deal_agent_framework.py        # Central agent coordinator & ChromaDB client
│   ├── price_is_right.py              # Market evaluation engine
│   ├── pricer_service.py              # Autonomous API tool server
│   ├── memory.json                    # Persistent session memory store
│   └── day1.ipynb - day5.ipynb        # Agent development progression
│
├── qlora_fine_tuning/                 # Core ML Parameter-Efficient Fine-Tuning
│   ├── jsonl/                         # Formatted instruction datasets
│   ├── redemption_train.ipynb         # QLoRA fine-tuning training loop (PEFT/TRL)
│   ├── redemption_run.ipynb           # Model evaluation & generation testing
│   └── day1.ipynb - day5.ipynb        # Fine-tuning labs and loss analysis
│
├── requirements.txt                   # Unified dependencies
└── README.md
```

## ⚙️ Setup & Execution

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
Create a `.env` file in the root directory:
```bash
OPENAI_API_KEY=your_openai_key
# Or local Ollama endpoint (e.g. OLLAMA_HOST=http://localhost:11434)
```

### 3. Launch the Multi-Agent Framework
```bash
cd autonomous_agents
python deal_agent_framework.py
```

### 4. Explore QLoRA Training Notebooks
```bash
cd qlora_fine_tuning
jupyter lab redemption_train.ipynb
```

## 📄 License
MIT License
