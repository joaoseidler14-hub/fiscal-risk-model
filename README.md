# Fiscal Risk Index

An interpretable **Fiscal Risk Index (FRI)** built from macroeconomic, demographic, external sector, and fiscal indicators obtained from the **World Bank (World Development Indicators)** and the **International Monetary Fund (Fiscal Monitor)**.

The project provides a transparent and reproducible framework to assess and compare fiscal vulnerability across countries using publicly available data.

---

## Overview

Fiscal sustainability plays a central role in macroeconomic stability and sovereign creditworthiness. Persistent fiscal deficits, rising public debt, weak economic performance and adverse demographic dynamics increase governments' exposure to fiscal stress.

This project develops a composite **Fiscal Risk Index (FRI)** using **Principal Component Analysis (PCA)** to summarize multiple dimensions of fiscal vulnerability into a single indicator.

The final index is scaled from:

* **0** → Lowest fiscal vulnerability
* **100** → Highest fiscal vulnerability

---

## Research Question

> Which countries exhibit the highest levels of fiscal vulnerability when macroeconomic, demographic, external sector and fiscal indicators are jointly considered?

---

## Data Sources

### World Bank – World Development Indicators (WDI)

* GDP per Capita
* Real GDP Growth
* Inflation Rate (Consumer Prices)
* GDP Deflator Inflation
* Compulsory Education Duration
* Population Aged 65+
* Age Dependency Ratio
* Unemployment Rate
* Government Revenue (% GDP)
* Government Expenditure (% GDP)
* Gross Capital Formation (% GDP)
* Gross Domestic Savings (% GDP)
* Exports of Goods and Services (% GDP)
* International Reserves (Months of Imports)

### International Monetary Fund – Fiscal Monitor

* Gross Government Debt (% GDP)
* Fiscal Balance (% GDP)

---

## Methodology

The project follows four stages:

### 1. Data Collection

* World Bank API
* IMF Fiscal Monitor API

### 2. Data Preprocessing

* Country harmonization
* Missing value imputation (country median)
* Dataset validation
* Construction of a country-year panel

### 3. Feature Engineering

Indicators are standardized before dimensionality reduction.

Variables expected to reduce fiscal vulnerability have their direction adjusted so that higher values consistently indicate greater fiscal risk.

### 4. Fiscal Risk Index

The Fiscal Risk Index is estimated using **Principal Component Analysis (PCA)**.

The first seven principal components are combined using their explained variance as weights to construct the final index.

Finally, the index is normalized to a 0–100 scale.

---

## Variables

### Macroeconomic

* GDP per Capita
* Real GDP Growth
* Inflation Rate
* GDP Deflator Inflation
* Unemployment Rate

### Fiscal

* Government Revenue (% GDP)
* Government Expenditure (% GDP)
* Gross Government Debt (% GDP)
* Fiscal Balance (% GDP)

### Demographic

* Population Aged 65+
* Age Dependency Ratio
* Compulsory Education Duration

### External Sector

* Gross Capital Formation (% GDP)
* Gross Domestic Savings (% GDP)
* Exports (% GDP)
* International Reserves (Months of Imports)

---

## Repository Structure

```text
fiscal-risk-model/

├── data/
│   ├── wdi.csv
│   ├── imf.csv
│   ├── ratings.xlsx
│   └── panel_final.csv
│
├── download.py
├── preprocess.py
├── index.py
│
├── requirements.txt
└── README.md
```

---

## Technologies

* Python
* Pandas
* NumPy
* Scikit-learn
* Requests
* World Bank API
* IMF SDMX API

---

## Future Improvements

* Validation against sovereign credit ratings (Moody's, S&P and Fitch)
* Factor Analysis
* Kernel PCA
* Autoencoder-based Fiscal Risk Index
* Fiscal crisis prediction models

---

## Author

**João Victor Freitas**

Economist • Data Scientist • Financial Risk Professional
