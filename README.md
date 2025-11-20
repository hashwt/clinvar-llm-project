# LLM-Assisted Pathogenicity Classification Using ClinVar
Team members
1) Harshil Watts (1002248670)
2) Mahesh Varma Sangaraju (1002237500)
3) Amruth Bhargav Katakam (1002237703)

## Overview
This project evaluates whether modern Large Language Models (LLMs)—specifically ChatGPT, Gemini, and Claude—can accurately classify genetic variants as **Pathogenic** or **Benign** based solely on their HGVS notation and gene symbol. ClinVar provides high-confidence expert-curated labels, which are used as the ground truth for benchmarking.

The goal is to compare LLM predictions against ClinVar labels and assess their reliability for genomic variant interpretation.

---

## Dataset
**Source:** ClinVar `variant_summary.txt.gz`  
**Download Location:** NCBI FTP (public access)

After processing, the dataset includes:

- **HGVS notation** (Name)
- **Gene symbol**
- Clinical significance
- Review status (star rating)
- Genomic coordinates
- VariationID

### Preprocessing Steps
All preprocessing was performed in Google Colab:
1. Downloaded ClinVar dataset via `wget`
2. Loaded selected columns using `pandas`
3. Filtered variants with:
   - Clear classifications (Pathogenic/Likely pathogenic, Benign/Likely benign)
   - High-confidence review status (≥2-star: “multiple submitters, no conflicts”, “expert panel”, “practice guideline”)
   - Removed VUS and conflicting interpretations
4. Created a **balanced 200-variant subset**
5. Exported the file as `clinvar_llm_sample.csv` for LLM evaluation

---

## Methods

### LLM Prompting
Each variant is converted into a standardized prompt:
Gene: {GeneSymbol}
Variant (HGVS): {Name}

Classify this variant as Pathogenic or Benign and provide a brief justification.


The same prompt is submitted to:
- **ChatGPT**
- **Gemini**
- **Claude**

### Evaluation
Model predictions are compared to ClinVar’s `SimpleLabel` column.

Metrics computed:
- Accuracy
- Precision / Recall
- Confusion matrix

Visualizations:
- Confusion matrices for each model
- Accuracy comparison bar chart

All analysis is performed in **Google Colab**.

---

## Repository Structure
/project/

│── data/

│ └── clinvar_llm_sample.csv

│
│── notebooks/

│ └── preprocessing_and_analysis.ipynb
│

│── results/

│ ├── confusion_matrix_chatgpt.png

│ ├── confusion_matrix_gemini.png

│ ├── confusion_matrix_claude.png

│ └── accuracy_plot.png
│

│── README.md

│── ai_usage.md


---

## Tools & Versions
- Google Colab (Python 3.12)
- pandas 2.x
- NumPy 1.x
- Matplotlib / Seaborn
- ChatGPT (OpenAI)
- Gemini (Google DeepMind)
- Claude (Anthropic)

---

## How to Run
1. Open the notebook in Google Colab  
2. Run Section 1 (Download ClinVar)
3. Run Section 2 (Filtering & preprocessing)
4. Upload the final `clinvar_llm_sample.csv` to each LLM
5. Collect predictions and upload results back to Colab
6. Run evaluation cells to generate metrics and plots




