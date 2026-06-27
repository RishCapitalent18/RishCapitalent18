# Hi, I'm Rishabh 👋

I'm an MS Computer Engineering grad from **Virginia Tech** (May 2026), specializing in AI and Data Analytics. I build things at the intersection of **data engineering, machine learning, and enterprise risk** — from LLM fine-tuning pipelines to fraud detection systems to GRC dashboards that actually get used.

Before grad school I spent 2+ years at **Wipro** as a Cybersecurity Analyst, where I ran risk assessments, built compliance pipelines, and designed the dashboards that helped teams track what actually mattered. That background shapes how I approach ML work: I think like an attacker, not just a builder - I care about pipelines being reproducible, metrics being interpretable, and results being auditable.

Currently open to **AI Engineer**, **ML Engineer**, and **Data Analyst** roles in the US — OPT, available immediately.

---

## 🛠 Tech Stack

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

## 🔬 Featured Projects

> *Projects marked \* are collaborative group work - I've described my specific contributions in each repo's README.*

---

### 🛡️ [LLM Guardrail Benchmark & Bypass Analyzer](https://github.com/RishCapitalent18/llm-guardrail-analyzer)
Built an adversarial benchmark to measure how well LLM safety guardrails hold up against real jailbreak attacks — combining AI engineering with offensive security thinking.

- Designed a **3-layer defense system**: regex/keyword filter (~1ms), HuggingFace toxicity classifier (~310ms), and a zero-shot NLI judge (~198ms) - same defense-in-depth architecture used by Meta's Llama Guard
- Built the **attack bench first**: 50 adversarial prompts across 10 categories (DAN, prompt injection, token smuggling, role-play, gradual escalation, authority impersonation, obfuscation, and more)
- Benchmark output: precision, recall, F1, per-layer catch rates, per-category bypass rates - answers "which attacks slip through, and which layer fails?" with data, not assumptions
- Streamlit dashboard with live prompt tester, bypass heatmap, and confusion matrix
- `HuggingFace Transformers` `NLI` `Streamlit` `Plotly` `AI Safety` `Adversarial ML`

---

### ☁️ [Fraud Detection API - AWS Lambda + S3](https://github.com/RishCapitalent18/aws-fraud-detector)
End-to-end MLOps pipeline: train a fraud detection model and deploy it serverlessly on AWS.

- Trained RandomForest on 1.3M transactions (ROC-AUC 0.9943); packaged and uploaded model artifact to S3
- Deployed inference endpoint on AWS Lambda (Python 3.13, 512MB) — cold start ~700ms, warm inference ~270ms
- Monitored via CloudWatch; architecture demonstrates full train → store → serve production loop
- `AWS Lambda` `S3` `CloudWatch` `scikit-learn` `Python`

---

### 📊 [Credit Card Fraud & Spending Analytics](https://github.com/RishCapitalent18/credit-card-sql-analytics)
SQL-driven fraud detection and spending analysis on 1.3M+ synthetic credit card transactions using DuckDB.

- Identified a **20–30× fraud rate spike at 10–11pm** vs daytime hours through hour-of-day aggregation
- Built anomaly detection flagging transactions > 2× a customer's baseline spend (surfaced 386× outliers)
- Segmented customers into HIGH / MEDIUM / LOW risk tiers using CTEs and CASE logic
- `DuckDB` `SQL` `Python` `pandas`

---

### 🔍 [Financial LLM Hallucination Detector](https://github.com/RishCapitalent18/financial-hallucination-detector)
Multi-signal hallucination detection pipeline for LLM-generated financial text — no API key required.

- Combines NLI entailment (`cross-encoder/nli-deberta-v3-small`), numerical consistency checking, and semantic similarity into a weighted hallucination score
- Streamlit dashboard with claim-by-claim breakdown, gauge chart, and pie chart; tested on IBM FinQA (87% SUPPORTED detection, 79% HALLUCINATED detection)
- `PyTorch` `HuggingFace Transformers` `Sentence-Transformers` `Streamlit` `spaCy`

---

### 🤖 [Large-Scale Reasoning Optimization via LLM Fine-Tuning](https://github.com/RishCapitalent18/Project-Reasoning-SFT-LLM) *
Fine-tuned **Qwen2.5-3B Instruct** using supervised fine-tuning (SFT) to improve multi-step reasoning reliability.

- Built end-to-end data preparation and training pipelines with dataset normalization, validation, and YAML/Bash-driven configuration for reproducible runs
- Automated evaluation workflows benchmarked against **AIME 2024/25** and **GPQA Diamond** — achieved **49.4% on GPQA Diamond** (a hard reasoning benchmark where many 7B+ models score below 40%)
- `PyTorch` `Hugging Face` `YAML` `Bash`

---

### 🧠 [Hallucination Mitigation in LLMs - Knowledge Graphs + MoE](https://github.com/RishCapitalent18/Fact-Checking-QnA-System--CG-and-MOEs) *
Designed a Knowledge-Graph-grounded Mixture-of-Experts QA system to reduce hallucinations in LLM outputs.

- Created and validated domain-specific datasets to analyze failure modes and expert routing behavior
- Trained on **Qwen2.5-3B**, reducing training loss below **0.1**; deployed Streamlit dashboards to monitor accuracy and fairness trends
- `PyTorch` `Knowledge Graphs` `Streamlit` `Qwen2.5`

---

### 🚨 [Credit Card Fraud Detection - End-to-End ML Pipeline](https://github.com/RishCapitalent18/credit-card-fraud-detection-ml)
Solo project. Built a fraud detection system combining **Self-Organizing Maps** for anomaly detection with a neural network classifier.

- Optimized probability-based scoring pipeline; achieved **93.19% detection accuracy**
- `TensorFlow` `Keras` `NumPy` `Pandas`

---

### 📦 [Real-Time Suspicious Baggage Detection - YOLO](https://github.com/RishCapitalent18/Suspicious-Baggage-Detection-System) *
YOLOv5-based object detection system for identifying suspicious items in real-time baggage screening.

- Improved F1-confidence and precision-recall curves using focal loss; achieved **90.35% accuracy**
- `YOLOv5` `Python` `OpenCV` `Streamlit`

---

## 💼 Work Highlights

**Path Perception & Validation Engineer — Victor Tango SAE, Virginia Tech** *(Sep 2024 – Aug 2025)*
Built a ROS-integrated MATLAB bench-testing framework to validate ADAS path perception pipelines. Engineered a PostgreSQL-backed Dijkstra routing system generating 4096-point waypoint arrays at ±1m centerline accuracy with <500ms response time.

**Cybersecurity Analyst L2 — GRC, Risk & Data Analytics @ Wipro** *(Apr 2022 – Aug 2024)*
Managed 140+ cybersecurity and cloud risk assessments through ServiceNow GRC. Designed risk-scoring models that surfaced 37% of critical risks earlier and cut remediation closure time by 25%. Built KPI dashboards used across compliance and security teams.

---

## 🔧 What I'm Exploring Next

- LLM output-side guardrails - extending the guardrail benchmark to check model responses, not just inputs
- GRPO-based reinforcement fine-tuning for multi-step reasoning tasks
- RAG pipeline optimization for domain-specific QA
- End-to-end analytics pipelines: raw data → insight → decision, not just model output

---

## 📫 Let's Connect

Actively looking for **AI Safety **, **AI Engineer** and **Data Analyst** roles where I can contribute from day one. OPT with STEM OPT option — no sponsorship needed to start.

[![LinkedIn](https://img.shields.io/badge/LinkedIn-rishabh--karthik--ramesh-0A66C2?style=flat&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/rishabh-karthik-ramesh/)
[![Email](https://img.shields.io/badge/Email-rishabhkramesh@gmail.com-EA4335?style=flat&logo=gmail&logoColor=white)](mailto:rishabhkramesh@gmail.com)

---
