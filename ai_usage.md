# AI Usage Documentation

This document describes how AI tools were used in this project and how correctness and reproducibility were ensured.

## Purpose of AI Use
AI was used in this project in **two distinct ways**:

### 1. **As part of the experiment**
LLMs (ChatGPT, Gemini, Claude) are evaluated as predictive models.  
Their outputs are collected and compared to ClinVar ground-truth labels.  
All prompts and responses will be saved or summarized in the final report.

### 2. **As a supportive tool**
ChatGPT was used to:
- Refine Python code for data filtering and sampling
- Provide debugging guidance for Colab issues

## Verification of AI Outputs
To ensure correctness:
- All AI-generated code changes was manually tested in Colab
- All logical steps and biological definitions were verified with official resources (ClinVar, HGVS guidelines)

## Summary
AI tools helped improve workflow efficiency and documentation quality, but final decisions, validations, and analysis were performed manually to ensure scientific accuracy and reproducibility.
