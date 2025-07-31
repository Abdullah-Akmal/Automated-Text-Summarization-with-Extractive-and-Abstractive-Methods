# Automated Text Summarization with Extractive and Abstractive Methods

## Problem Statement

Manually reading and summarizing lengthy documents is time-consuming and often inconsistent. This project demonstrates how Natural Language Processing (NLP) can automate text summarization using both extractive and abstractive techniques. It provides a comparative view of both approaches in terms of performance, readability, and summarization quality using objective evaluation metrics.

## Objectives

- Implement extractive and abstractive summarization techniques
- Preprocess and clean raw text data for NLP tasks
- Apply classical algorithms (TextRank) and transformer models (BART, T5)
- Evaluate summaries using ROUGE metrics
- Compare trade-offs between extractive and abstractive methods

## Tools and Libraries Used

| Category           | Tools and Libraries                                     |
|--------------------|----------------------------------------------------------|
| Programming Language | Python                                                 |
| NLP Libraries       | nltk, spaCy, gensim, summa (TextRank)                  |
| Transformers        | Hugging Face Transformers (BART, T5)                   |
| Evaluation Metrics  | datasets (ROUGE), rouge_score, scikit-learn            |
| Utilities           | pandas, NumPy, Jupyter Notebook                         |

## Methodology / Steps

### 1. Environment Setup
- Installed and imported all required NLP libraries
- Ensured compatibility for Hugging Face models and evaluation metrics

### 2. Data Preparation
- Used a sample article on COVID-19’s impact on remote work, tourism, and technology
- Applied basic preprocessing (tokenization, stopword removal)

### 3. Extractive Summarization
- Technique: TextRank algorithm using the `summa` library
- Approach: Extracted top 30% of sentences based on importance
- Sample Output:
  "Many companies have shifted to remote working models, which has led to a reevaluation of work-life balance..."

### 4. Abstractive Summarization
- Technique: `facebook/bart-large-cnn` model via Hugging Face Transformers
- Approach: Generated human-like summaries with min_length=30 and max_length=100
- Sample Output:
  "The rise of remote working has changed how we work, reducing stress but impacting industries like tourism."

### 5. Evaluation
- Metric: ROUGE (Recall-Oriented Understudy for Gisting Evaluation)
- Comparison: Abstractive summary evaluated against extractive summary (as reference)
- Results:
  - ROUGE-1 F1: 0.28
  - ROUGE-2 F1: 0.15
  - ROUGE-L F1: 0.23

### 6. Reporting and Visualization
- Displayed extractive and abstractive summaries side-by-side
- Visualized ROUGE scores (Precision, Recall, F1) for comparison

## Outcome and Insights

### Technical Summary

| Method       | Strengths                       | Limitations                             |
|--------------|----------------------------------|------------------------------------------|
| Extractive   | High factual accuracy            | Can be verbose and redundant             |
| Abstractive  | Human-like and concise summaries | May introduce semantic inconsistencies   |

### Business Applications

- Summarizing news articles, market reports, and research papers
- Reducing long documents (e.g., legal, academic, feedback) into digestible formats
- Speeding up content comprehension for analysts and decision-makers

## Limitations and Future Enhancements

- Reference Bias: ROUGE may penalize valid abstractive summaries if extractive summaries are used as reference
- Future Improvements:
  - Use human-written summaries as references
  - Explore domain-specific models (e.g., SciBERT, PubMedBERT)
  - Evaluate using BERTScore for semantic similarity

## Key Takeaway

This project presents a production-ready text summarization pipeline using both traditional and transformer-based NLP methods. It highlights the trade-offs between extractive and abstractive summarization and demonstrates a scalable framework for automated summarization of large volumes of unstructured text.
