# Practical Statistics for Data Scientists (O'Reilly)
### Code Reproduction & Theoretical Deep-Dive for Machine Learning & Deep Learning

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Python 3.8+](https://img.shields.io/badge/python-3.8+-blue.svg)](https://www.python.org/downloads/)

<p align="center">
  <img src="./cover.jpeg" alt="Practical Statistics for Data Scientists Cover" width="220" />
</p>

This repository contains the complete code reproduction, theoretical explanations, mathematical deep-dives, and chapter-by-chapter summaries for **Chapters 1 through 4** based on the reference textbook **"Practical Statistics for Data Scientists: 50+ Essential Concepts Using R and Python"** (2nd Edition) by Peter Bruce, Andrew Bruce, and Peter Gedeck (O'Reilly Media).

---

### Student Identity

| Attribute | Details |
| :--- | :--- |
| **Nama** | **Fransisco Sitepu** |
| **Kelas** | **TK 47 03** |
| **Mata Kuliah** | **Machine Learning** |
| **Tugas** | **TUGAS 1 (Enrichment Individual Task) - Code Reproduction & Theoretical Deep-Dive** |
| **Buku Referensi** | *Practical Statistics for Data Scientists* (O'Reilly Media) |
| **Repository URL** | [https://github.com/Frans1828/Practical-Statistics-for-Data-Scientists](https://github.com/Frans1828/Practical-Statistics-for-Data-Scientists) |

---

## Table of Contents

- [Overview](#overview)
- [Repository Structure](#repository-structure)
- [Chapter Summaries](#chapter-summaries)
  - [Chapter 1: Exploratory Data Analysis](#chapter-1-exploratory-data-analysis)
  - [Chapter 2: Data and Sampling Distributions](#chapter-2-data-and-sampling-distributions)
  - [Chapter 3: Statistical Experiments and Significance Testing](#chapter-3-statistical-experiments-and-significance-testing)
  - [Chapter 4: Regression and Prediction](#chapter-4-regression-and-prediction)
- [Datasets](#datasets)
- [Installation and Environment Setup](#installation-and-environment-setup)
- [References & Links](#references--links)

---

## Overview

The objective of this project is to bridge core statistical principles with practical machine learning implementation. Statistical concepts are foundational to data exploration, hypothesis formulation, feature engineering, and model validation.

Each notebook reproduces the book's examples using Python scientific libraries (`pandas`, `numpy`, `scipy`, `statsmodels`, `seaborn`, `matplotlib`, `wquantiles`, `scikit-learn`) accompanied by rigorous theoretical explanations, mathematical formulations, and practical data science takeaways.

---

## Repository Structure

```plaintext
.
├── PracticalStatisticsChapter1.ipynb   # Chapter 1: Exploratory Data Analysis
├── PracticalStatisticsChapter2.ipynb   # Chapter 2: Data and Sampling Distributions
├── PracticalStatisticsChapter3.ipynb   # Chapter 3: Statistical Experiments and Significance Testing
├── PracticalStatisticsChapter4.ipynb   # Chapter 4: Regression and Prediction
├── requirements.txt                    # Python library dependencies
├── _config.yml                         # Jekyll configuration for GitHub Pages
├── cover.jpeg                          # Book cover image
├── README.md                           # Main repository documentation & chapter summaries
└── data/                               # Directory containing all reference datasets
    ├── state.csv
    ├── dfw_airline.csv
    ├── sp500_sectors.csv
    ├── sp500_data.csv.gz
    ├── kc_tax.csv.gz
    ├── lc_loans.csv
    ├── airline_stats.csv
    ├── loans_income.csv
    ├── web_page_data.csv
    ├── four_sessions.csv
    ├── click_rates.csv
    ├── imanishi_data.csv
    ├── LungDisease.csv
    └── house_sales.csv
```

---

## Chapter Summaries

### Chapter 1: Exploratory Data Analysis
**Notebook:** [`PracticalStatisticsChapter1.ipynb`](./PracticalStatisticsChapter1.ipynb)

Exploratory Data Analysis (EDA), pioneered by John W. Tukey, emphasizes that data investigation, pattern visualization, and metric summarization must precede any modeling attempt.

- **Data Taxonomies**: Distinguishes numeric variables (continuous, discrete) and categorical variables (nominal, ordinal, binary) to guide proper metric and visualization choices.
- **Estimates of Location**:
  - *Mean vs. Median*: Arithmetic mean is sensitive to extreme values. Robust measures like the **trimmed mean** and **median** provide reliable location metrics in skewed or contaminated distributions.
  - *Weighted Mean & Weighted Median*: Account for varying reliability or unequal representation across observations.
- **Estimates of Variability**:
  - *Standard Deviation & Variance*: Measure dispersion around the mean, but squared terms amplify outlier sensitivity.
  - *Median Absolute Deviation (MAD)* & *Interquartile Range (IQR)*: Robust dispersion metrics resilient against heavy tails.
- **Exploring Distributions**:
  - *Boxplots*: Summarize median, 25th/75th percentiles (IQR), and outliers.
  - *Histograms & Density Estimates (KDE)*: Provide continuous approximations of probability density functions (PDF), exposing multi-modality and skewness.
- **Multivariate Analysis**:
  - Scatterplots, Hexagonal Binning, 2D Contour Plots, Violin Plots, and FacetGrids.

---

### Chapter 2: Data and Sampling Distributions
**Notebook:** [`PracticalStatisticsChapter2.ipynb`](./PracticalStatisticsChapter2.ipynb)

Contrasts underlying population distributions with the sampling distribution of an estimator, providing the foundation for statistical inference.

- **Random Sampling and Selection Bias**: Quality exceeds quantity - large sample sizes cannot compensate for systematic bias.
- **Central Limit Theorem (CLT)**: The sampling distribution of the sample mean converges toward a normal distribution as sample size `n` increases.
- **Standard Error (SE)**: Quantifies sampling variability: `SE = s / sqrt(n)`
- **The Bootstrap**: Non-parametric resampling technique drawing repeated samples *with replacement* to estimate confidence intervals without parametric assumptions.
- **Confidence Intervals**: A 95% confidence interval implies 95% of such constructed intervals across repeated samplings contain the true population parameter.
- **Parametric Distributions**:
  - *Normal Distribution*: Bell curve characterized by mean (mu) and standard deviation (sigma).
  - *Student's t-Distribution*: Heavier tails than normal for small-sample inferences.
  - *Binomial Distribution*: Success counts in `n` independent Bernoulli trials with probability `p`.
  - *Poisson & Exponential*: Event counts per interval (Poisson, rate lambda) and waiting times (Exponential, mean 1/lambda).
  - *Weibull Distribution*: Survival and reliability analysis with shape `k` and scale `lambda` parameters.

---

### Chapter 3: Statistical Experiments and Significance Testing
**Notebook:** [`PracticalStatisticsChapter3.ipynb`](./PracticalStatisticsChapter3.ipynb)

Focuses on experimental design to prove causality and distinguish true effects from random noise.

- **A/B Testing & Controlled Experiments**: Compares Treatment vs. Control groups under randomized allocation.
- **Permutation Tests**: Non-parametric, free from normality or variance-homogeneity assumptions.
- **Statistical Significance & p-Values**: The probability of observing a result as extreme as the test statistic, assuming H0 is true.
- **Type I Error (alpha)**: Rejecting H0 when it is actually true (false positive).
- **Type II Error (beta)**: Failing to reject H0 when a true effect exists (false negative).
- **Multiple Testing**: Corrections (Bonferroni, FDR) are mandatory when evaluating multiple variants.
- **Parametric Tests**:
  - *t-Test*: Comparing two independent sample means.
  - *ANOVA*: Comparing means across three or more groups using the F-statistic.
  - *Chi-Square Test*: Testing independence in categorical contingency tables.
- **Multi-Arm Bandits (MAB)**: Reinforcement learning framework balancing exploration and exploitation.
- **Power & Sample Size**: Pre-experiment power analysis (commonly 80%) ensures experiments are sufficiently powered.

---

### Chapter 4: Regression and Prediction
**Notebook:** [`PracticalStatisticsChapter4.ipynb`](./PracticalStatisticsChapter4.ipynb)

Establishes the foundation of predictive modeling, evaluating relationships between predictors and a continuous outcome.

- **Simple & Multiple Linear Regression**: OLS estimates parameters by minimizing Sum of Squared Errors (SSE).
- **Model Evaluation**:
  - *RMSE & MAE*: Quantify prediction error in native target units.
  - *R-squared*: Proportion of total response variance explained by predictors.
  - *Adjusted R-squared*: Penalizes additional features to prevent misleading increases in R-squared.
- **Model Selection**: AIC and BIC criteria with forward/backward stepwise selection.
- **Factor Variables & Encoding**: Converts categorical features with `k` levels into `k - 1` dummy indicators (dummy variable trap prevention).
- **Regression Diagnostics**:
  - *Residual Analysis*: Evaluates homoskedasticity, linearity, and error normality.
  - *Cook's Distance*: Identifies observations that disproportionately shift model parameters.
  - *VIF*: Detects multicollinearity among predictors.
- **Non-Linear Extensions**:
  - *Polynomial Regression*: Captures curvature via higher-order terms.
  - *Spline Regression & GAMs*: Piecewise polynomials smoothly joined at knots.

---

## Datasets

All datasets referenced across the four notebooks are stored in the [`data/`](./data/) directory:

| Dataset | File | Description | Primary Chapter |
| :--- | :--- | :--- | :--- |
| US State Stats | `state.csv` | Population, murder rates, and state metrics | Chapter 1 |
| DFW Flight Delays | `dfw_airline.csv` | Categorical flight delay counts at DFW airport | Chapter 1 |
| S&P 500 Sectors | `sp500_sectors.csv` | Sector classification for S&P 500 equities | Chapter 1 |
| S&P 500 Prices | `sp500_data.csv.gz` | Historical stock price time-series | Chapter 1, 2 |
| King County Tax | `kc_tax.csv.gz` | Assessed property values and living square footage | Chapter 1 |
| LendingClub Loans | `lc_loans.csv` | Borrower grades, loan status, and recovery rates | Chapter 1 |
| Airline Stats | `airline_stats.csv` | Carrier-specific delay percentages | Chapter 1 |
| Loans Income | `loans_income.csv` | Sampling distributions of borrower annual income | Chapter 2 |
| Web Page Data | `web_page_data.csv` | Page session times for A/B testing | Chapter 3 |
| Four Sessions | `four_sessions.csv` | Session stickiness across 4 page versions (ANOVA) | Chapter 3 |
| Click Rates | `click_rates.csv` | Headline click-through test counts (Chi-Square) | Chapter 3 |
| Imanishi Data | `imanishi_data.csv` | Experimental digit test data | Chapter 3 |
| Lung Disease | `LungDisease.csv` | Peak expiratory flow rate vs. exposure years | Chapter 4 |
| House Sales | `house_sales.csv` | King County real estate transaction features | Chapter 4 |

---

## Installation and Environment Setup

### 1. Clone the Repository
```bash
git clone https://github.com/Frans1828/Practical-Statistics-for-Data-Scientists.git
cd Practical-Statistics-for-Data-Scientists
```

### 2. Set Up Virtual Environment (Recommended)
```bash
python -m venv venv
# On Windows:
venv\Scripts\activate
# On Linux/macOS:
source venv/bin/activate
```

### 3. Install Dependencies
```bash
pip install --upgrade pip
pip install -r requirements.txt
```

### 4. Launch Jupyter Notebook
```bash
jupyter notebook
```

---

## References & Links

1. **Primary Reference Book**:
   Bruce, P., Bruce, A., & Gedeck, P. (2020). *Practical Statistics for Data Scientists: 50+ Essential Concepts Using R and Python* (2nd ed.). O'Reilly Media.
   - [Book Resource on Google Drive](https://drive.google.com/file/d/1dR9228_PRCN5_Hjs9ClxYgKe5zmifkmb/view?usp=sharing)

2. **Official Book Repository**:
   [gedeck/practical-statistics-for-data-scientists](https://github.com/gedeck/practical-statistics-for-data-scientists)

3. **Reference Submission Example**:
   [farrelrassya/Practical-Statistics-for-Data-Scientist-Books](https://github.com/farrelrassya/Practical-Statistics-for-Data-Scientist-Books)

---

## Academic Integrity & Notes

This repository was created as an individual submission for **TUGAS 1 (Enrichment for Machine Learning and Deep Learning Classes)**. All code reproductions and theoretical deep-dives adhere to academic integrity standards. Explanations and syntheses have been curated to provide comprehensive educational value.

**Nama: Fransisco Sitepu | Kelas: TK 47 03 | Mata Kuliah: Machine Learning**
