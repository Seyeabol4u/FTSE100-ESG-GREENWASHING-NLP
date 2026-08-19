# Analytical Workflow

## 1. Overview

This document summarises the computational workflow used in the MSc Business Analytics dissertation examining potential greenwashing signals in FTSE 100 corporate sustainability reporting.

The analytical process combines corporate sustainability-report text, Natural Language Processing (NLP), company-level sentiment and topic measures, and LSEG ESG performance data.

The workflow is organised into three principal analytical notebooks.

---

## 2. Text Extraction and Preprocessing

Corporate sustainability reports for the final sample of 25 FTSE 100 companies were processed using Python.

The preprocessing workflow included:

- PDF text extraction;
- corpus validation;
- text cleaning and normalisation;
- removal of non-informative textual elements;
- tokenisation and linguistic preprocessing;
- preparation of validated text for subsequent NLP analysis.

The purpose of this stage was to transform the original sustainability-report corpus into a structured textual dataset suitable for topic modelling and sentiment analysis.

Relevant notebook:

`01_Text_Preprocessing_and_LDA_Topic_Modelling.ipynb`

---

## 3. LDA Topic Modelling

Latent Dirichlet Allocation (LDA) was used to identify recurring sustainability-related themes within the processed report corpus.

The principal stages included:

- preparation of the processed corpus;
- construction of the LDA modelling inputs;
- estimation and evaluation of candidate topic solutions;
- selection and interpretation of the final topic structure;
- assignment of interpretable sustainability topic labels;
- calculation of topic distributions;
- aggregation of topic measures to company level.

The final analytical framework contained 14 sustainability topics.

The company-level output is provided in:

`outputs/Company_Level_LDA_Topic_Distribution.csv`

---

## 4. FinBERT Sentiment Analysis

FinBERT was applied to the validated sustainability-report text to assess the sentiment characteristics of corporate sustainability disclosures.

The analysis estimated:

- positive sentiment probability;
- negative sentiment probability;
- neutral sentiment probability;
- continuous sentiment score.

Segment-level FinBERT results were subsequently aggregated to company level to support integration with the LDA and ESG datasets.

Relevant notebook:

`02_FinBERT_Sentiment_Analysis.ipynb`

Company-level output:

`outputs/Company_Level_FinBERT_Sentiment.csv`

---

## 5. LSEG ESG Performance Data

LSEG ESG performance measures were used as the external indicators of corporate ESG performance.

Four measures were incorporated into the analytical workflow:

- Overall ESG Score;
- Environmental Score;
- Social Score;
- Governance Score.

The Overall ESG Score served as the principal dependent variable in the subsequent statistical analysis.

The underlying LSEG ESG data are not redistributed through this repository because they are subject to third-party access and licensing conditions.

---

## 6. Data Integration

Company identifiers (`C01`–`C25`) were used to ensure consistent matching across the analytical datasets.

The company-level LDA topic distributions, FinBERT sentiment measures and LSEG ESG performance measures were validated before integration.

One observation was retained for each of the 25 sampled companies.

Relevant notebook:

`03_Statistical_Analysis.ipynb`

---

## 7. Statistical Analysis

The integrated company-level dataset was analysed using:

- descriptive statistics;
- Pearson correlation analysis;
- Variance Inflation Factors (VIF);
- multiple linear regression;
- regression diagnostic procedures.

The statistical analysis examined whether company-level disclosure characteristics derived from LDA and FinBERT were associated with variation in LSEG ESG performance.

The analytical framework was designed to identify disclosure–performance relationships that may represent potential greenwashing signals. These relationships are interpreted as screening indicators rather than direct evidence of intentional greenwashing.

---

## 8. Notebook Execution Order

The notebooks should be reviewed and executed in the following sequence:

1. `01_Text_Preprocessing_and_LDA_Topic_Modelling.ipynb`
2. `02_FinBERT_Sentiment_Analysis.ipynb`
3. `03_Statistical_Analysis.ipynb`

Outputs generated during the earlier analytical stages are used as inputs during subsequent stages.

---

## 9. Reproducibility Considerations

The notebooks preserve the principal analytical procedures used in the dissertation.

Users attempting to reproduce the complete workflow should note that:

- local file paths reflect the original research environment and may require modification;
- the original corporate sustainability reports are not stored in this repository;
- access to the relevant LSEG ESG data may be required;
- required Python packages are listed in the root-level `requirements.txt`;
- the spaCy English language model `en_core_web_sm` must be installed separately.

The repository is intended to provide transparent documentation of the analytical procedures while respecting third-party data-access and licensing restrictions.
