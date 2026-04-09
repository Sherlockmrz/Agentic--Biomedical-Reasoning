# Plan–Act–Verify for CURE-Bench  
### An Agentic Biomedical Reasoning System with Tool-Augmented Evidence Retrieval

 Presented as a conference abstract at **MIDI 2025**

---

##  Overview

This repository presents **Plan–Act–Verify**, a two-pass agentic system for **therapeutic reasoning** on the **CURE-Bench** benchmark.

The system integrates large language models with curated biomedical tools to improve factual grounding, reduce hallucination, and support structured clinical decision-making.

---

##  Key Highlights

- 📊 Evaluated on the **CURE-Bench** therapeutic reasoning benchmark  
- 🧩 Designed a **two-pass agentic pipeline (Plan → Act → Verify)**  
- 🔬 Integrated biomedical tools: FDA, DailyMed, MedlinePlus, RxNav, OpenTargets, PubChem  
- 🏆 Achieved **0.69564 accuracy** with fine-tuned GPT-4.1 + tools  
- 🎤 Selected for presentation at **MIDI 2025 (conference abstract)**  

---

##  System Architecture

###  Pass 1 — Plan
- Analyze question + options  
- Extract key entities (drugs, conditions)  
- Identify required medical facts  
- Select relevant tools  

###  Pass 2 — Act + Verify
- Query curated biomedical tools  
- Retrieve structured evidence  
- Filter, deduplicate, and compress into **Tool Facts**  
- Feed evidence back into the model  
- Generate final answer  

---

##  Tool Ecosystem

The system uses a curated subset of high-value biomedical tools:

- **FDA APIs** — indications, warnings, contraindications  
- **DailyMed** — official drug labels  
- **MedlinePlus** — patient-level summaries  
- **RxNav / RxNorm** — drug interactions and normalization  
- **OpenTargets** — research evidence  
- **PubChem** — chemical and compound information  

---

##  Results

| Model | Accuracy |
|------|---------:|
| GPT-4.1 | 0.520 |
| GPT-4.1 + tools | 0.543 |
| GPT-4.1-Finetuned | 0.671 |
| GPT-4.1-Finetuned + tools | **0.69564** |
| GPT-5 + tools | 0.687 |

###  Key Findings

- Tool augmentation provides consistent performance gains  
- Fine-tuning delivers the largest improvement  
- Combining both yields the best results  

---

##  Example Workflow

1. Input: clinical question + multiple choices  
2. Planner identifies relevant drugs and facts  
3. Tools retrieve evidence (FDA, DailyMed, etc.)  
4. Evidence is summarized into **Tool Facts**  
5. Model outputs final answer  

---

##  Reproducibility

This project includes:

- Structured submission generation (`submission.csv`)  
- Metadata tracking (`metadata.json`)  
- Tool usage logs and reasoning traces  
- Checkpoint-based execution pipeline  

---

##  Conference Recognition

**Plan–Act–Verify: An Agentic AI Question Answering and Reasoning System Evaluated on the CURE-Bench Challenge**

- Presented as a **conference abstract at MIDI 2025**
- Included in the **MIDI 2025 virtual venue**

---

##  Limitations

- Single-round tool calling  
- Benchmark-specific evaluation  
- Possible inconsistencies across biomedical sources  
- Fine-tuning may introduce overfitting  

---

##  Future Work

- Multi-step iterative tool reasoning  
- Improved conflict resolution across sources  
- Stronger patient-context modeling  
- Evaluation on broader medical benchmarks  

---

##  Author

Ruize Ma  
New York University
