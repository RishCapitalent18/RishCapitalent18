# Hey, I'm Rishabh 👋

MS Computer Engineering from **Virginia Tech** (May 2026), focused on AI and Data Analytics. I spend most of my time building things where machine learning meets real-world risk and fraud detection, safety guardrails, agentic systems, hallucination pipelines. The kind of stuff that has to actually work, not just score well on a benchmark.

Before grad school I spent 2+ years at **Wipro** as a Cybersecurity Analyst - running risk assessments, building compliance pipelines, and designing dashboards that security teams actually used. That background sticks with me. I think like a detective, not just a builder - I care about pipelines being reproducible, metrics being interpretable, and results being auditable.

Looking for **AI Safety**, **AI Engineer**, **ML Engineer**, or **Data Analyst** roles in the US. 

---

# 🛠 Tech Stack

**Languages**

![Python](https://img.shields.io/badge/Python-3776AB?style=flat&logo=python&logoColor=white)
![SQL](https://img.shields.io/badge/SQL-4479A1?style=flat&logo=postgresql&logoColor=white)
![MATLAB](https://img.shields.io/badge/MATLAB-0076A8?style=flat&logo=mathworks&logoColor=white)

**ML / AI**

![PyTorch](https://img.shields.io/badge/PyTorch-EE4C2C?style=flat&logo=pytorch&logoColor=white)
![TensorFlow](https://img.shields.io/badge/TensorFlow-FF6F00?style=flat&logo=tensorflow&logoColor=white)
![Keras](https://img.shields.io/badge/Keras-D00000?style=flat&logo=keras&logoColor=white)
![Hugging Face](https://img.shields.io/badge/HuggingFace-FFD21E?style=flat&logo=huggingface&logoColor=black)

**Data & Analytics**

![Pandas](https://img.shields.io/badge/Pandas-150458?style=flat&logo=pandas&logoColor=white)
![NumPy](https://img.shields.io/badge/NumPy-013243?style=flat&logo=numpy&logoColor=white)
![Spark](https://img.shields.io/badge/Apache%20Spark-E25A1C?style=flat&logo=apachespark&logoColor=white)
![Tableau](https://img.shields.io/badge/Tableau-E97627?style=flat&logo=tableau&logoColor=white)
![Streamlit](https://img.shields.io/badge/Streamlit-FF4B4B?style=flat&logo=streamlit&logoColor=white)

**Cloud & Tools**

![AWS](https://img.shields.io/badge/AWS-232F3E?style=flat&logo=amazonaws&logoColor=white)
![Azure](https://img.shields.io/badge/Microsoft%20Azure-0078D4?style=flat&logo=microsoftazure&logoColor=white)
![ServiceNow](https://img.shields.io/badge/ServiceNow-62D84E?style=flat&logo=servicenow&logoColor=white)
![PostgreSQL](https://img.shields.io/badge/PostgreSQL-336791?style=flat&logo=postgresql&logoColor=white)

**Certifications:** Azure SC-900 · AZ-900 · AI-900 · DP-900

---

# 🔬 Featured Projects

> *Projects marked \* are group work — my specific contributions are in each repo's README.*

---

## 🎸 [Music Agent Red Team — Agentic AI Security Demo](https://github.com/RishCapitalent18/music-agent-redteam)
I built a music theory AI agent and then attacked it — not through the user query, but through the retrieval corpus and tool outputs. The goal was to show where agentic AI systems actually break, and why an input-side safety filter doesn't help you there.

- Ran three attack types against a live ReAct agent: indirect prompt injection (poisoned content in retrieved artist bios), tool poisoning (compromised tool returning adversarial payloads), and goal hijacking (injecting a new objective mid-reasoning chain)
- Built both obvious and subtle variants of each attack — obvious ones use keywords like "SYSTEM OVERRIDE" and get caught, subtle ones use indirect scope-expansion language and slip past the detector entirely; that gap is the point
- Red team results: 86% precision, 67% recall, 1 false positive — the false positive came from a totally normal query that happened to contain "my new goal is", which shows how brittle keyword-based detection really is
- Pairs with the LLM Guardrail Benchmark below — together they cover both ends of the safety problem: blocking bad inputs and securing what happens after
- `ReAct Agent` `Agentic AI Security` `Red Teaming` `Prompt Injection` `Streamlit`

---

## 🛡️ [LLM Guardrail Benchmark & Bypass Analyzer](https://github.com/RishCapitalent18/llm-guardrail-analyzer)
I wanted to know how well LLM safety guardrails actually hold up — not in theory, but against real attack prompts. So I built the attack set first, then built the defense, then measured it.

- Three-layer defense: a fast regex filter (~1ms), a HuggingFace toxicity classifier (~310ms), and a zero-shot NLI judge (~198ms) — same layered architecture used in Meta's Llama Guard
- 50 adversarial prompts across 10 categories: DAN, prompt injection, token smuggling, role-play, gradual escalation, authority impersonation, obfuscation, and more
- Outputs precision, recall, F1, per-layer catch rates, and per-category bypass rates — so you can actually see which attacks slip through and which layer is letting them
- Streamlit dashboard with a live prompt tester, bypass heatmap, and confusion matrix; runs fully local, no API key needed
- `HuggingFace Transformers` `NLI` `Streamlit` `Plotly` `AI Safety` `Adversarial ML`

---

## ☁️ [Fraud Detection API - AWS Lambda + S3](https://github.com/RishCapitalent18/aws-fraud-detector)
Trained a fraud detection model and deployed it as a live serverless API on AWS — full train-to-serve loop.

- RandomForest on 1.3M transactions, ROC-AUC 0.9943; model artifact packaged and stored in S3
- Deployed on AWS Lambda (Python 3.13, 512MB) — cold start around 700ms, warm inference around 270ms
- Monitored via CloudWatch; the whole thing is meant to show what a real deployment looks like, not just a notebook
- `AWS Lambda` `S3` `CloudWatch` `scikit-learn` `Python`

---

## 📊 [Credit Card Fraud & Spending Analytics](https://github.com/RishCapitalent18/credit-card-sql-analytics)
SQL fraud detection and spending analysis across 1.3M+ synthetic credit card transactions in DuckDB.

- Found a 20–30× fraud rate spike at 10–11pm vs. daytime - just from hour-of-day aggregation
- Built anomaly detection that flags transactions more than 2× a customer's own baseline spend; surfaced 386× outliers
- Segmented customers into HIGH / MEDIUM / LOW risk tiers using CTEs and CASE logic
- `DuckDB` `SQL` `Python` `pandas`

---

## 🔍 [Financial LLM Hallucination Detector](https://github.com/RishCapitalent18/financial-hallucination-detector)
A multi-signal pipeline for catching hallucinations in LLM-generated financial text — no API key required.

- Combines NLI entailment, numerical consistency checking, and semantic similarity into a single weighted hallucination score
- Tested on IBM FinQA: 87% on supported claims, 79% on hallucinated ones; Streamlit dashboard shows claim-by-claim breakdowns
- `PyTorch` `HuggingFace Transformers` `Sentence-Transformers` `Streamlit` `spaCy`

---

## 🤖 [Large-Scale Reasoning Optimization via LLM Fine-Tuning](https://github.com/RishCapitalent18/Project-Reasoning-SFT-LLM) *
Fine-tuned Qwen2.5-3B Instruct on supervised fine-tuning (SFT) to improve how reliably it handles multi-step reasoning.

- Built the full data prep and training pipeline — normalization, validation, YAML/Bash-driven config so runs are reproducible
- Evaluated against AIME 2024/25 and GPQA Diamond; hit 49.4% on GPQA Diamond, which is where a lot of 7B+ models struggle to break 40%
- `PyTorch` `Hugging Face` `YAML` `Bash`

---

## 🧠 [Hallucination Mitigation in LLMs — Knowledge Graphs + MoE](https://github.com/RishCapitalent18/Fact-Checking-QnA-System--CG-and-MOEs) *
A knowledge-graph-grounded Mixture-of-Experts QA system designed to reduce hallucinations in LLM outputs.

- Built and validated domain-specific datasets to study failure modes and how experts get routed
- Trained on Qwen2.5-3B, got training loss below 0.1; Streamlit dashboards to track accuracy and fairness
- `PyTorch` `Knowledge Graphs` `Streamlit` `Qwen2.5`

---

## 🚨 [Credit Card Fraud Detection - End-to-End ML Pipeline](https://github.com/RishCapitalent18/credit-card-fraud-detection-ml)
Solo project combining Self-Organizing Maps for anomaly detection with a neural network classifier.

- Probability-based scoring pipeline; 93.19% detection accuracy
- `TensorFlow` `Keras` `NumPy` `Pandas`

---

## 📦 [Real-Time Suspicious Baggage Detection - YOLO](https://github.com/RishCapitalent18/Suspicious-Baggage-Detection-System) *
YOLOv5 object detection for identifying suspicious items in real-time baggage screening.

- Used focal loss to improve F1 and precision-recall curves; 90.35% accuracy
- `YOLOv5` `Python` `OpenCV` `Streamlit`

---

# 💼 Work

**Path Perception & Validation Engineer — Victor Tango SAE, Virginia Tech** *(Sep 2024 – Aug 2025)*
Built a ROS-integrated MATLAB bench-testing framework to validate ADAS path perception pipelines. Built a PostgreSQL-backed Dijkstra routing system that generates 4096-point waypoint arrays at ±1m centerline accuracy with under 500ms response time.

**Cybersecurity Analyst L2 — GRC, Risk & Data Analytics @ Wipro** *(Apr 2022 – Aug 2024)*
Managed 140+ cybersecurity and cloud risk assessments through ServiceNow GRC. Built risk-scoring models that surfaced 37% of critical risks earlier and cut remediation closure time by 25%. Built the KPI dashboards that compliance and security teams actually used day-to-day.

---

# 🔧 What I'm Working On Next

- Output-side guardrails for agentic systems — extending the music agent red team with a response scanner that catches subtle attacks the input filter misses
- GRPO-based reinforcement fine-tuning for multi-step reasoning
- RAG pipeline optimization for domain-specific QA
- End-to-end analytics: raw data to actionable insight, not just model output

---

# 📫 Let's Connect

Looking for **AI Safety**, **AI Engineer**, and **Data Analyst** roles where I can contribute from day one. OPT with STEM extension — no sponsorship needed to start.

[![LinkedIn](https://img.shields.io/badge/LinkedIn-rishabh--karthik--ramesh-0A66C2?style=flat&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/rishabh-karthik-ramesh/)
[![Email](https://img.shields.io/badge/Email-rishabhkramesh@gmail.com-EA4335?style=flat&logo=gmail&logoColor=white)](mailto:rishabhkramesh@gmail.com)

---
