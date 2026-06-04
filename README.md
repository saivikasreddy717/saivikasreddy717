# Sai Vikas Reddy Yeddulamala

**AI/ML Engineer** who teaches language models to stop making things up. In pharma. Where making things up is frowned upon.

> Somewhere between a fraud-detection graph network and a heavy set of squats, there is a man who really likes systems that actually work in production.

Hey, you found my corner of GitHub. This README is a bit of a choose-your-own-adventure. Click the little arrows to go deeper, or skim the top and bail. I built it the way I build software: readable on the surface, with depth underneath if you want it.

---

<details>
<summary>📖 <b>Chapter 1: The Origin Story</b> (click me)</summary>

<br>

I started at **Tata Consultancy Services** in India, where my job was essentially to tell banks which transactions were lying. I built a fraud-detection system on a graph of cards, devices, and merchants (GraphSAGE plus XGBoost, with a TCN for the short impatient sequences), and it caught more fraud while running faster. Fraudsters: 0. Me: a noticeably better precision-recall curve.

I also built recommendation systems (two-tower retrieval, DeepFM reranking) and a banking assistant that resolved roughly 55% of conversations without escalating to a human. That is either a triumph of NLP or a quiet commentary on how repetitive banking questions are. Probably both.

</details>

<details>
<summary>💊 <b>Chapter 2: Present Day, Cardinal Health</b> (click me)</summary>

<br>

Now I build **GenAI and agentic systems** for pharmaceutical compliance. The central challenge: the AI is not allowed to hallucinate when the subject is drug recalls and shortages. It turns out that "please be confidently wrong less often" is an entire engineering discipline.

So I build the unglamorous, important machinery that makes that real:

- Agentic compliance workflows on **LangGraph** with **MCP** tools, stateful routing, and human-in-the-loop guardrails
- **RAG** pipelines with hybrid retrieval, ColBERT reranking, and RAGAS evals (3x retrieval precision, 40% less analyst grunt work)
- **LoRA/QLoRA** fine-tuned 7B models that pull structured data out of regulatory documents at 98% exact match
- **vLLM** plus **NVIDIA Triton** inference serving, 8x throughput, p95 latency under 150ms
- **MLOps** on **AWS EKS** that dragged deployment from weeks down to days

M.S. in Computer Science (Data Science) from NC State. AWS ML Engineer and Azure Data Scientist certified. I read AI alignment papers for fun, which is a sentence that has cost me dearly at parties.

</details>

---

### 🧰 The Arsenal

<details>
<summary><b>Open the toolbox</b></summary>

<br>

**GenAI & LLMs:** LangGraph, LangChain, MCP, RAG, GraphRAG, multi-agent orchestration, LoRA/QLoRA, PEFT, DPO, GRPO, DSPy, structured outputs, guardrails

**Inference & Serving:** vLLM, NVIDIA Triton, TensorRT-LLM, FlashAttention, quantization, ONNX

**ML & Deep Learning:** PyTorch, TensorFlow, XGBoost, LightGBM, GraphSAGE, two-tower models, DeepFM, FSDP

**MLOps & Cloud:** AWS (SageMaker, EKS, Lambda), GCP Vertex AI, Databricks, Snowflake, Kubernetes, MLflow, Docker

**Evaluation & Observability:** RAGAS, Langfuse, Promptfoo, LLM-as-judge

</details>

---

### 🔬 The Exhibits

Three things I built that I am actually willing to put my name on.

<details>
<summary><b>Exhibit A: rag-eval-harness</b> (stop guessing which RAG strategy is best)</summary>

<br>

Most teams pick naive dense retrieval because it is the default, ship it, and discover six months later that hybrid or reranking would have halved their hallucinations. This harness turns "which strategy should I use?" into an empirical question with a three-command answer.

It runs 5 retrieval strategies (naive, hybrid BM25 plus dense with RRF fusion, cross-encoder rerank, HyDE, multi-query) against the same question set, scores each with RAGAS, and produces a side-by-side scorecard with cost and latency. Swap Groq, OpenAI, Ollama, or Gemini by editing two lines of YAML, no code changes. It also scores agent traces (tool selection, execution success, multi-step coherence) and runs online eval over sampled production streams. 145 tests, all mocked, zero API keys required in CI.

`Python` `FAISS` `LangChain` `RAGAS` `Pydantic v2`

Repo: [github.com/saivikasreddy717/rag-eval-harness](https://github.com/saivikasreddy717/rag-eval-harness)

</details>

<details>
<summary><b>Exhibit B: MCP observability platform</b> (currently under construction, hard hat required)</summary>

<br>

Compliance-grade observability for agentic AI: distributed tracing, evals, and guardrail monitoring for MCP-based tool-calling workflows. Built so that when an agent does something strange in production, you can actually find out what happened and why, instead of staring at a log file and sighing.

Shipping in a few days. Watch the repo if you enjoy a good cliffhanger.

`MCP` `LangGraph` `OpenTelemetry` `Evals`

</details>

<details>
<summary><b>Exhibit C: STGATT</b> (a graph network that fills in the blanks)</summary>

<br>

A sandwich-style spatial-temporal GNN for multivariate time-series imputation, because real sensor data shows up full of holes and someone has to fix that. It pairs a dynamic graph construction mechanism (sparse, directed, top-50% edges) with an encoder-only Transformer using learnable positional encoding, capturing spatial and temporal structure at the same time.

Benchmarked against FFN, BiGRU, Transformer, and T-GCN on real-world sensor datasets including SWaT, then stress-tested for robustness as missing-data rates climbed from 20% all the way to 80%. It held up. The baselines, less so.

`PyTorch` `GNN` `Transformers`

Repo: [github.com/saivikasreddy717/STGATT](https://github.com/saivikasreddy717/STGATT)

</details>

---

### 🎬 Plot Twist

<details>
<summary><b>Things the resume does not mention</b></summary>

<br>

- I train 5 days a week on a push/pull/legs split and hold opinions about progressive overload that I will share entirely unprompted.
- I cook, mostly Indian food, and I treat recipes like ablation studies. One variable at a time.

</details>

---

### 🤝 The Part Where We Talk

If you are building real production AI and want someone who has actually shipped it, and who will not let the model quietly lie to your users, let's talk.

- **LinkedIn:** [linkedin.com/in/saivikasy](https://www.linkedin.com/in/saivikasy/)
- **Email:** saivikas.y@zohomail.com

> Currently open to AI Engineer, ML Engineer, LLM Engineer, and GenAI roles. Remote or hybrid in SF, NYC, Seattle, or Raleigh. Will relocate for sufficiently interesting problems.
