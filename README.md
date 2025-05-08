# Paper 1. PPA Subtype Classification Benchmark

This repository presents a comprehensive benchmark for **Primary Progressive Aphasia (PPA) subtype classification** using a wide range of NLP features and machine learning models. The goal is to evaluate and compare traditional, embedding-based, and transformer-based techniques on clinically transcribed speech data.

---

## Project Timeline and Evolution

### Initial Work Submitted to ACL 2025

We developed and submitted a benchmark framework to ACL 2025, which included:

- **Dataset**: Transcribed speech from PPA patients describing the Western Aphasia Battery picnic scene.
- **Feature Extraction**:
  - Classical: `TF-IDF`, `BoW`, `N-grams (2–4)`, `LSA`, `LDA`
  - Embedding-based: `Word2Vec`, `GloVe`, `FastText`
  - Syntactic: `Dependency Parsing`
  - Transformers: `BERT`, `RoBERTa`, `ClinicalBERT`, `MentalBERT`
- **Models**: `Logistic Regression`, `SVM`, `MLP`, `Naive Bayes`, `XGBoost`, `BERT`, `RoBERTa`, `ClinicalBERT`, `MentalBERT`, and prompting-based classification with `GPT-3.5`, `GPT-4o-mini`, `LLaMA 3`, and `Mistral`
- **Evaluation Metrics**: `F1-score`, `Balanced Accuracy`, `Precision`, `Recall`, `Hamming Loss`, `AUC`  
  *(5-fold Stratified Cross-Validation was used in initial experiments)*

---

## Post-Submission Limitations Identified

After submission, we identified and addressed key limitations based on reviewer feedback:

| Reviewer Concern                                           | Resolution |
|------------------------------------------------------------|------------|
|  TF-IDF and BoW computed on the full dataset             |  Fixed using fold-specific pipelines |
|  Sentence-level splits caused speaker leakage            |  Fixed using `GroupKFold` by participant |
|  Surprisingly high results from simple features          |  Reevaluated using corrected setup |
|  Missing interpretability and feature insights           |  Plan to include feature importance analysis |
|  Small dataset acknowledged                              |  Discussed and justified in clinical context |
|  GitHub repo not accessible at review time               |  Will be publicly available and documented |

---

##  Resubmission to EMNLP 2025

We are currently preparing a revised and extended version of this work for **EMNLP 2025**, with a planned submission by:

 **Deadline**: May 19, 2025

###  Improvements for EMNLP

-  Fold-specific feature extraction via pipelines
-  Use of `GroupKFold` to prevent speaker leakage
-   Feature importance analysis (`model.coef_`, SHAP)

---

##  Summary of Experiments

| Category             | Methods                                                                 |
|---------------------|-------------------------------------------------------------------------|
| **Classical Features**  | TF-IDF, BoW, N-grams, LSA, LDA                                          |
| **Embeddings**          | Word2Vec, GloVe, FastText                                              |
| **Syntax-Based**        | Dependency Parsing                                                     |
| **Transformer Models**  | BERT, RoBERTa, ClinicalBERT, MentalBERT                                |
| **LLMs (Prompting)**    | GPT-3.5, GPT-4o-mini, LLaMA 3, Mistral                                 |
| **Classifiers**         | Logistic Regression, SVM, MLP, Naive Bayes, XGBoost                    |

---

## Team & Acknowledgements

This benchmark is part of a research collaboration focused on language analysis for neurodegenerative diseases. We gratefully acknowledge our clinical collaborators, dataset providers, and the reviewers for their insightful feedback which has helped us significantly improve this work.

---




