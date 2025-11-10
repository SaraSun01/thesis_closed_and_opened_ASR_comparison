# Comparative Evaluation of Closed- and Open-Vocabulary ASR Systems for Dutch Healthcare Terms  

This repository contains the code and analysis for my MSc Voice Technology thesis at the **University of Groningen (Campus Fryslân, Netherlands)**.  
The study compares **closed-vocabulary** (Kaldi TDNN) and **open-vocabulary** (K2 Pruned RNN-T) ASR systems on **Dutch healthcare transcripts**, with a focus on domain-specific terminology (diseases, drugs, abbreviations, person names and brand names).

---

## 🎯 Research Overview  

### Objectives  
- Compare performance of a **closed-vocabulary model** (Kaldi TDNN) and an **open-vocabulary model** (K2 RNN-T) on **Dutch clinical speech** (~42.5 hours). 
Medium
- Evaluate models using **general error metrics** (WER/CER) and **specialized metrics** for healthcare terms (Medical-WER, Medical-CER, term-level precision/recall). 
Medium
- Identify which model type is better for structured, **domain-specific terminology** versus **flexible, evolving entities**, and explore how their strengths might be combined.

### Key Findings  
- 🩺 **The closed-vocabulary system** (Kaldi TDNN) shows higher precision and lower Medical-WER for standardized clinical terminology. 
Medium
- 💬 **The open-vocabulary system** (K2 RNN-T) performs better in recall and shows lower Medical-CER on variable or emergent entities (e.g., brand names, informal speech). 
- 📊 The results suggest that a hybrid approach, leveraging closed-vocabulary reliability for known terms and open-vocabulary flexibility for new/unseen terms, may lead to more robust ASR in healthcare contexts

*(See full thesis or Medium summary below for detailed results and visualizations.)*

---

## ⚙️ Project Structure  

| File | Description |
|------|--------------|
| `01_extract_SNOMED_medical_terms.py` | Extracts healthcare terms from SNOMED-CT terminology |
| `02_filter_out_medical_terms.py` | Filters identified medical terms in transcripts |
| `03_named_entity_recognition.py` | Runs SpaCy-based entity extraction |
| `04_global_alignment.py` | Performs global alignment between ASR and gold transcripts |
| `05_ngram_term_matching.py` | N-gram-based matching for fuzzy recognition |
| `06_fuzzy_matching.py` | Computes fuzzy match scores using RapidFuzz |
| `07_precision_recall_F1.py` | Evaluates precision, recall, and F1 for identified terms |
| `08_medical_WER_CER.py` | Calculates Medical-WER and Medical-CER |
| `09_visualization.ipynb` | Generates analysis plots and summary figures |
| `10_summary_stats.py` | Summarizes key coverage and performance metrics |

---

## 🧩 Requirements

Please install the following Python packages before running the scripts:

- `pandas`  
- `rapidfuzz`  
- `spacy`  
- `editdistance`  
- `jiwer`  

You can install them using pip:

```bash
pip install pandas rapidfuzz spacy editdistance jiwer
```

## 🚀 Quick Start  

1. Clone this repository  
   ```bash
   git clone https://github.com/SaraSun01/thesis_closed_and_opened_ASR_comparison.git
   cd thesis_closed_and_opened_ASR_comparison
2. Install dependencies
   ```bash
   pip install -r requirements.txt
3. Follow the processing order:
   ```bash
   python 01_extract_SNOMED_medical_terms.py
   python 02_filter_out_medical_terms.py
   ...
   python 10_summary_stats.py
---
*(Due to data privacy agreements, original Dutch healthcare transcripts are not included.)*


## 📚 Resources

📄 Full Thesis (PDF): https://campus-fryslan.studenttheses.ub.rug.nl/662/

📰 Medium Article Summary: [https://medium.com/@s.sun.19/closed-vs-open-vocabulary-asr-in-healthcare-what-works-best-for-dutch-healthcare-speech-c862131d04db]

## 🪶 License
See the [LICENSE](./LICENSE) file for more details.
