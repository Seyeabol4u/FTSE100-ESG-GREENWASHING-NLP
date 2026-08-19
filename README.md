# Detecting Greenwashing Signals in FTSE 100 Sustainability Reports

This repository contains the analytical code and non-restricted supporting outputs for an MSc Business Analytics dissertation examining potential greenwashing signals in corporate sustainability reporting.

The study applies Natural Language Processing (NLP) and statistical analysis to sustainability disclosures from 25 FTSE 100 companies. The analytical framework combines Latent Dirichlet Allocation (LDA) topic modelling, FinBERT sentiment analysis and independently assessed ESG performance measures from the London Stock Exchange Group (LSEG).

## Research Aim

The project investigates how NLP techniques, integrated with statistical analysis, can be used to identify disclosure–performance relationships that may indicate potential greenwashing signals in FTSE 100 corporate sustainability reports.

The analysis is intended as an analytical screening framework rather than an automated mechanism for proving intentional greenwashing.

## Analytical Workflow

The research workflow consists of three principal stages:

1. **Text Extraction, Preprocessing and LDA Topic Modelling**
   - extraction of text from corporate sustainability reports;
   - corpus validation and cleaning;
   - text preprocessing;
   - document segmentation;
   - LDA topic modelling;
   - aggregation of topic distributions to company level.

2. **FinBERT Sentiment Analysis**
   - preparation of validated text segments;
   - FinBERT sentiment classification;
   - estimation of positive, negative and neutral sentiment probabilities;
   - calculation of a continuous sentiment score;
   - aggregation of sentiment measures to company level.

3. **ESG Integration and Statistical Analysis**
   - integration of company-level LDA and FinBERT outputs with LSEG ESG performance measures;
   - descriptive statistical analysis;
   - Pearson correlation analysis;
   - multicollinearity assessment;
   - multiple linear regression;
   - regression diagnostics and hypothesis evaluation.

## Repository Structure

```text
FTSE100-ESG-GREENWASHING-NLP/
│
├── notebooks/
│   ├── 01_Text_Preprocessing_and_LDA_Topic_Modelling.ipynb
│   ├── 02_FinBERT_Sentiment_Analysis.ipynb
│   ├── 03_Statistical_Analysis.ipynb
│   └── README.md
│
├── outputs/
│   ├── Company_Level_LDA_Topic_Distribution.csv
│   ├── Company_Level_FinBERT_Sentiment.csv
│   └── README.md
│
├── documentation/
│   └── analytical_workflow.md
│
├── .gitignore
├── requirements.txt
└── README.md
## Notebook Execution Order

The notebooks should be reviewed and executed in the following order:

1. `01_Text_Preprocessing_and_LDA_Topic_Modelling.ipynb`
2. `02_FinBERT_Sentiment_Analysis.ipynb`
3. `03_Statistical_Analysis.ipynb`

The outputs generated during the earlier analytical stages are used as inputs to the subsequent stages.

## Python Dependencies

The principal Python packages used in the project are listed in `requirements.txt`.

Install the required packages using:

```bash
pip install -r requirements.txt

FinBERT Model

Sentiment analysis uses the pretrained ProsusAI/finbert model through the Hugging Face Transformers library.

FinBERT is applied to validated sustainability-report text to estimate positive, negative and neutral sentiment probabilities.

Data Availability

Corporate sustainability reports used in the research were obtained from publicly available company and investor-relations websites.

The original corporate reports are not redistributed through this repository.

LSEG ESG data used in the dissertation are subject to third-party access and licensing conditions and are therefore not publicly redistributed through this repository.

The outputs/ directory contains non-restricted derived analytical outputs used to support the dissertation findings.

Sample

The final analytical sample consists of 25 FTSE 100 companies representing multiple industry sectors.

Company identifiers C01 to C25 are used throughout the analytical workflow to maintain consistency between the text-analysis outputs and statistical datasets.

Reproducibility

The repository documents the principal computational procedures used in the dissertation and is intended to provide transparency regarding the analytical workflow.

Local file paths appearing in the notebooks reflect the original research environment and may need to be updated by users wishing to reproduce the analysis on another computer.

Access to the original corporate reports and LSEG ESG data may also be required to reproduce the complete workflow from raw data.

Dissertation

Programme: MSc Business Analytics
Institution: University of Greenwich
Module: BUSI1783 – Business Analytics Project
Year: 2026

Author

Seye David Abolade
