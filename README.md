# LLM-Assisted Pathogenicity Classification Using ClinVar
Team members
1) Harshil Watts (1002248670)
2) Mahesh Varma Sangaraju (1002237500)
3) Amruth Bhargav Katakam (1002237703)

## Overview
# LLM-Assisted Classification of ClinVar Variants

This project benchmarks the ability of Large Language Models (ChatGPT, Gemini, Claude) to classify genetic variants as **Pathogenic** or **Benign** using only **HGVS notation** and **gene symbols**.  
Ground-truth variant labels were obtained from **ClinVar**, filtered to include only high-confidence (≥2-star) submissions.

The goal is to evaluate whether LLMs can recognize biologically meaningful mutation patterns from HGVS strings alone—without access to external genomic databases.

## 📁 Project Structure

data/

clinvar_llm_sample.csv

chatgpt.csv

gemini.csv

claude.csv


notebooks/

LLM_ClinVar_Benchmark.ipynb

results/

llm_accuracy_comparison_bar_chart.png

chatgpt_confusion_matrix.png

gemini_confusion_matrix.png

claude_confusion_matrix.png

final_llm_predictions.csv


environment.yml

README.md

ai_usage.md


---

## 🧬 Dataset Summary

- **Source:** ClinVar (variant_summary.txt.gz)  
  https://ftp.ncbi.nlm.nih.gov/pub/clinvar/tab_delimited/

- **Filtering steps:**
  - Kept only *Pathogenic / Likely Pathogenic* and *Benign / Likely Benign*
  - Removed VUS, conflicting interpretations, and low-confidence review statuses
  - Limited to variants with ≥2-star review confidence

- **Benchmark dataset:**  
  A balanced set of **200 variants** (100 pathogenic-like, 100 benign-like)  
  → Saved as: `data/clinvar_llm_sample.csv`

This filtered dataset is appropriate because it provides reliable, expert-reviewed labels needed for evaluating LLM prediction performance.

---

## 🛠 Methods Overview

1. **Preprocessing**  
   Extracted and cleaned relevant columns (HGVS notation, gene symbol, clinical significance, review status).

2. **Prompt Design**  
   Each model received the same standardized prompt containing:
   - HGVS notation (from ClinVar “Name” field)  
   - GeneSymbol  

   No ClinVar labels or external information were given to the LLMs.

3. **LLM Predictions**  
   Predictions were collected manually from ChatGPT, Gemini, and Claude.  
   Saved as separate files in `data/`.

4. **Benchmarking**  
   Using Python (pandas, scikit-learn, matplotlib):
   - Accuracy  
   - Precision, recall, F1-score  
   - Confusion matrices  
   - Accuracy comparison bar chart  

Notebook:  
`notebooks/LLM_ClinVar_Benchmark.ipynb`

---

## 📊 Key Results

| Model     | Accuracy |
|-----------|----------|
| Claude    | **89%**  |
| Gemini    | **88%**  |
| ChatGPT   | **82.5%** |

**Common error pattern:**  
Pathogenic variants were more likely to be misclassified as benign, reflecting the difficulty of interpreting subtle pathogenic signals without biological context.

All visualizations are available in the **results/** folder.

---

## 🔁 Reproducibility

To reproduce the analysis:

1. Clone the repository.  
2. Create the environment:

conda env create -f environment.yml
conda activate llm-clinvar-benchmark


3. Open and execute the notebook:

notebooks/LLM_ClinVar_Benchmark.ipynb


All computations (metrics, plots, merging predictions) run end-to-end using this environment.

---

## 🤖 AI Use Disclosure

See **ai_usage.md** for full transparency.

Summary:
- ChatGPT was used for writing support, code refinement, formatting, and presentation assistance.
- All benchmarking predictions were collected manually.
- LLMs were **never** provided ClinVar labels.
- All results and interpretation steps were manually verified.

---

## 📚 References

- Landrum MJ, et al. ClinVar: improving access to variant interpretations and supporting evidence. *Nucleic Acids Research*.  
- NCBI ClinVar Database: https://www.ncbi.nlm.nih.gov/clinvar/

---

## 🙏 Acknowledgments

- Dr. Jeffery Demuth  
- NCBI ClinVar  
- Course materials and peers




