# AI Student Support System

An autonomous campus advisory and policy assistant built for the **TNSDC Virtual Internship Program – IBM Agentic AI Track**. The system couples **Retrieval-Augmented Generation (RAG)**, deterministic **Python Tool Calling**, and an **Alias Mapping Layer** to answer student inquiries across institutional handbooks without hallucinations.

---

## Key Features

* **Grounded Policy Retrieval (RAG):** Evaluates student queries against 7 campus regulatory domains (academics, grooming, hostel, OD/leave, exams, discipline, placements) using Cosine Vector Similarity.
* **Alias Mapping Layer:** Standardizes colloquial student slang, abbreviations, and informal terms (`bunk`, `od`, `gatepass`, `beard`, `coe`) into formal database keys.
* **Deterministic Tool Calling:** Routes numerical attendance calculations directly to a dedicated Python engine to verify exam clearance (75% threshold, 65% condonation) instead of relying on generative LLM estimates.
* **Conversational Memory:** Preserves multi-turn dialogue context across interactions.
* **Zero Cloud Dependency:** Operates fully self-contained using core Python structures, avoiding API quotas and heavy vector database overhead.

---

## System Architecture
User Query (Terminal / Chat)
│
▼
[Alias Mapping Layer] ────────── Resolves slang, acronyms, and informal phrases
│
▼
[Agent Intent Router Engine]
├──► [Math Engine Tool] ── Deterministic attendance calculation (75% rule)
└──► [Vector RAG Tool] ─── Cosine Similarity across 7 campus domains
│
▼
Synthesized Contextual Output + Session Memory Buffer

---

## Project Structure

```text
├── ibm.py                               # Core agent logic, tools, and interactive CLI
├── generate_pdf.py                      # Automated PDF report generator
├── AI_Student_Support_System_Report.pdf # Final compiled project report
├── requirements.txt                     # Project dependencies
└── README.md                            # Project documentation
