# AI Usage Documentation

This document explains how AI tools were used in this project and how correctness, integrity, and reproducibility were maintained.

---

## 1. Purpose of AI Use

AI was used in two distinct ways:

### **A. As part of the experiment**
Large Language Models (ChatGPT, Gemini, and Claude) were benchmarked as predictive tools.  
Their outputs were collected using standardized prompts and compared directly to ClinVar ground-truth classifications.  
These predictions were treated strictly as experimental results.

### **B. As a supportive tool**
ChatGPT (this assistant) was used to:
- Refine Python code structure and improve readability  
- Assist with debugging common Colab errors  
- Suggest ways to organize the notebook, results, and GitHub structure  
- Improve clarity and organization   

At no point did AI automate the full analysis workflow; it only supported human-driven tasks.

---

## 2. What AI *Did Not* Do

To maintain academic integrity:

- LLMs were **not** given ClinVar labels at any time.  
- LLMs were **not** used to compute accuracy, confusion matrices, or evaluation metrics.  
- LLMs did **not** determine conclusions without human review.  
- No external databases or hidden tools were accessed by AI.  
- The final scientific analysis and interpretation were performed manually.

All predictions used for benchmarking were collected manually from each LLM.

---

## 3. Verification of AI Outputs

To ensure correctness and reproducibility:

- All AI-suggested code was manually reviewed and executed in Colab to confirm correctness.
- All biological logic (HGVS notation, variant meanings, ClinVar terminology) was cross-checked with official resources.
- All intermediate and final results (metrics, plots, merged datasets) were independently validated by the student.
- All preprocessing steps and evaluation scripts are contained in the repository for transparency.

No result in the final analysis was accepted without manual verification.

---

## 4. Summary Statement

AI tools helped with:
- Code refinement  
- Workflow organization  
- Documentation and writing clarity  


However:
- All scientific decisions
- All preprocessing and analysis steps
- All evaluation metrics
- All experimental conclusions

were performed manually to ensure accuracy and reproducibility.

This project complies fully with course AI-use guidelines.

