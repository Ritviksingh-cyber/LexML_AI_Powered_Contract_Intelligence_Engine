
---

# ⚖️ Contract Viewer

### Contract Analysis and In-Depth Intuition Engine

An AI-powered **Hybrid (ML + RAG)** system for analyzing, extracting, and comparing clauses across legal contracts using **Legal-BERT, FAISS retrieval, and QA models**.

Built for scalable, intelligent contract understanding using the **CUAD dataset**.

---

## 🚀 Overview

Contract Viewer is designed to automate **legal contract analysis**, reducing manual effort and improving accuracy through:

* 📄 Clause extraction (rule-based + ML)
* 🤖 Legal-BERT multi-label classification
* ❓ Context-aware Question Answering (SQuAD BERT)
* ⚠️ Risk scoring and analysis
* 📊 Multi-contract comparison
* ⚡ Parallel processing for scalability
---


📤 Upload Interface

📊 Analysis Results

🔄 Multi-Contract Comparison

⚡ Batch Processing
---

## 🧠 Architecture

```id="arch-flow"
User Contract(s)
      │
      ▼
[Text Extraction + Preprocessing]
      │
      ▼
[Smart Chunking]
      │
      ├───────────────┬─────────────────────┐
      ▼               ▼                     ▼
[FAISS Retrieval] [Legal-BERT Classifier] [Rule-Based Extraction]
      │               │                     │
      └───────────────┴──────────────┬──────┘
                                     ▼
                            [QA Model (SQuAD BERT)]
                                     │
                                     ▼
                          [Risk Scoring Engine]
                                     │
                                     ▼
                         [Multi-Contract Comparison]
                                     │
                                     ▼
                             [Gradio UI Output]
```

---

## 🔍 Core Features

### 1. Hybrid Clause Extraction

* Combines:

  * Rule-based logic (regex patterns)
  * Legal-BERT classification
* Ensures both **precision + contextual understanding**

---

### 2. FAISS-Based Retrieval

* Enables fast semantic search across contract chunks
* Supports:

  * Multi-document querying
  * Context filtering before QA

---

### 3. Question Answering Engine

* Model: **SQuAD BERT**
* Extracts answers directly from contract context
* Works on:

  * Single contract
  * Multiple contracts

---

### 4. Risk Scoring System

* Custom scoring logic based on:

  * Missing clauses
  * Risky terms
* Produces:

  * Structured risk output
  * Comparable contract metrics

---

### 5. Multi-Contract Comparison

* Compare multiple contracts simultaneously
* Highlights:

  * Clause differences
  * Risk variations

---

### 6. Parallel Processing

* Speeds up:

  * Document ingestion
  * Analysis pipeline
* Uses concurrent execution for scalability

---

## 🛠️ Tech Stack

* **Python**
* **PyTorch**
* **HuggingFace Transformers**
* **FAISS**
* **Gradio**
* **PyMuPDF (fitz)**
* **Pandas**

---

## 📊 Dataset

* **CUAD v1 (Contract Understanding Atticus Dataset)**

  * 510 commercial contracts
  * 13,000+ labeled clauses
  * 41 clause categories

---

## ⚙️ Models Used

| Task               | Model                     |
| ------------------ | ------------------------- |
| Classification     | `legal-bert-base-uncased` |
| Question Answering | SQuAD BERT                |
| Retrieval          | FAISS (dense embeddings)  |

---

## ⚡ Key Design Decisions

### 1. Hybrid ML + Retrieval Instead of Pure RAG

Instead of relying only on retrieval, the system combines:

* Legal-BERT → structured understanding
* FAISS → fast semantic search
* QA → precise extraction

👉 This improves reliability in legal contexts where wording varies heavily.

---

### 2. Rule-Based + ML Combination

Pure ML misses deterministic patterns like dates or parties.
Rules ensure:

* High precision for known structures
* ML handles semantic complexity

---

### 3. Chunk-Based Processing

Contracts are split into smaller chunks to:

* Fit model constraints
* Improve retrieval accuracy
* Enable parallel execution

---

### 4. Custom Risk Scoring

Instead of generic outputs:

* Domain-inspired scoring logic is applied
* Makes results actionable (not just descriptive)

---

## 🚧 Limitations

* Long contracts may reduce QA accuracy due to context limits
* Rule-based extraction may fail on uncommon phrings
* Retrieval quality depends on chunking strategy
* No persistent storage for uploaded contracts (session-based)

---

## 🔮 Future Improvements

* Fine-tune domain-specific Legal LLM
* Add explainable AI (XAI) for risk decisions
* Deploy as API / SaaS platform
* Improve long-document handling with better chunking

---

## ▶️ How to Run

```bash
pip install transformers torch faiss-cpu gradio pymupdf pandas
```

```bash
# Run notebook or script
jupyter notebook contract_viewer.ipynb
```

---

## 🌐 UI

* Interactive interface using **Gradio**
* Upload contracts
* Ask questions
* Compare multiple documents
* View risk scores

---

## 👨‍💻 Author

**Ritvik Singh**
AI/ML Engineer

🔗 LinkedIn: [https://www.linkedin.com/in/ritvik-singh-94581a204/](https://www.linkedin.com/in/ritvik-singh-94581a204/)

---

## 🧠 Final Insight

This project focuses on **practical legal AI**, balancing:

* Speed (FAISS + parallelism)
* Accuracy (Legal-BERT + QA)
* Interpretability (risk scoring + rules)

---
