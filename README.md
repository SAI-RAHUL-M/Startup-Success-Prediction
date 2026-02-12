# 🚀 Startup Success Prediction

> **Can we predict whether a startup will succeed (IPO/Acquired) or fail (Closed) based on early-stage characteristics?**

## 📌 Project Overview
Startups are high-risk ventures, with a failure rate notoriously high. This project analyzes a dataset of **923 global startups** to identify key drivers of success. By examining factors like funding rounds, total investment, relationships, and milestones, we aim to build a machine learning model that predicts whether a startup will eventually be **Acquired/IPO** (Success) or **Closed** (Failure).

This project covers the full Data Science lifecycle:
1. **Data Pre-processing:** Cleaning messy real-world data.
2. **Exploratory Data Analysis (EDA):** Uncovering trends in geography, funding, and networking.
3. **Feature Engineering:** Creating predictive features from raw data.
4. **Machine Learning:** Training and evaluating models (Logistic Regression, Decision Trees, Random Forest).

---

## 📊 The Data
* **Source:** [Kaggle Startup Success Prediction Dataset](https://www.kaggle.com/datasets/manishkc06/startup-success-prediction/)
* **Size:** 923 Startups, 49 Features.
* **Target Variable:** `status` (Acquired/IPO vs. Closed).
* **Key Features:**
  * `funding_total_usd`: Total capital raised.
  * `milestones`: Number of major achievements (product launches, etc.).
  * `relationships`: Number of strategic partnerships/network size.
  * `state_code`: Geographic location (e.g., CA, NY, TX).
  * `funding_rounds`: Number of investment rounds.

---

## 🛠️ Methodology

### 1. Data Cleaning & Pre-processing
* **Duplicate Removal:** Identified and removed duplicate startup entries.
* **Imputation:** Handled missing values in `age_first_funding_year` and `age_last_funding_year` using median imputation. Filled categorical gaps with "Unknown".
* **Outlier Handling:** Winsorized extreme financial values (1st/99th percentile) to prevent model skew.
* **Standardization:** Normalized text data (lowercase, strip whitespace) for consistency.

### 2. Exploratory Data Analysis (EDA)
* **Univariate Analysis:** Analyzed distributions of funding (highly skewed) and milestones (discrete).
* **Bivariate Analysis:** Correlated `relationships` and `milestones` with success rates.
* **Geographic Analysis:** Investigated if startups in **California (CA)** or **New York (NY)** actually succeed more often than others.

### 3. Machine Learning Models
We trained and evaluated the following models to predict the binary outcome (`is_success`):
* **Logistic Regression:** Baseline model for interpretability.
* **Decision Tree:** To capture non-linear decision boundaries.
* **Random Forest:** The best-performing model, robust against overfitting.

---

## 🔑 Key Findings & Insights
1. **Execution > Money:** Surprisingly, the **number of milestones** and **relationships** were stronger predictors of success than the total funding amount.
2. **The "Network Effect":** Startups with larger networks (more relationships) had a significantly higher likelihood of IPOs.
3. **Location Nuance:** While **California** has the highest *volume* of startups, it does not necessarily have a higher *success rate* compared to hubs like Massachusetts (MA).
4. **Survivor Bias:** The dataset contains ~64% successful companies, which is higher than the real-world average. This suggests "survivor bias" in the data collection, which was accounted for during analysis.

---

## 💻 Getting Started

### Prerequisites
* Python 3.8+
* Jupyter Notebook / Google Colab

### Installation
1. Clone this repository:
   ```bash git clone [https://github.com/yourusername/startup-success-prediction.git](https://github.com/yourusername/startup-success-prediction.git)```
2. Install required packages:
   ```pip install pandas numpy seaborn matplotlib scikit-learn scipy```
4. Run the notebook:
   ```jupyter notebook Final.ipynb```

---

## 📈 Future Work
* Fixing Survivor Bias: Integrate a dataset with more "failed" companies to create a realistic class balance (90% failure / 10% success).
* Founder Experience: Scrape external data (e.g., LinkedIn) to include founder background, which is a massive unmeasured variable in this analysis.
* Text Analysis: Use NLP on startup descriptions to detect buzzwords associated with success.

This project was completed as part of the Principles of Data Science course.
