# fiscal-risk-model

# Fiscal Risk Index

An interpretable fiscal risk index built using macroeconomic, demographic, external sector and fiscal indicators from the World Bank (WDI) and the International Monetary Fund (Fiscal Monitor).

## Project Overview

Fiscal sustainability is a key determinant of economic stability and sovereign creditworthiness. Governments facing persistent deficits, rising debt burdens, adverse demographic trends and weak economic growth are more vulnerable to fiscal stress.

This project develops a Fiscal Risk Index (FRI) to measure and compare fiscal vulnerability across countries using publicly available data.

The objective is to build a transparent and reproducible framework capable of identifying countries with higher levels of fiscal fragility.

## Research Question

Which countries exhibit the highest levels of fiscal vulnerability when considering fiscal, macroeconomic, demographic and external sector indicators?

## Data Sources

### World Bank - World Development Indicators (WDI)

* GDP per capita
* Real GDP Growth
* Deposit Interest Rate
* Inflation Rate
* GDP Deflator Inflation
* Unemployment Rate
* Fertility Rate
* Population Aged 65+
* Age Dependency Ratio
* Government Revenue (% GDP)
* Government Expenditure (% GDP)
* Current Account Balance (% GDP)
* External Debt (% GNI)
* Gross Capital Formation (% GDP)
* International Reserves (Months of Imports)

### International Monetary Fund (Fiscal Monitor)

* Gross Debt (% GDP)
* Net Debt (% GDP)
* Fiscal Balance (% GDP)
* Primary Balance (% GDP)
* Cyclically Adjusted Primary Balance (% GDP)

## Methodology

The project follows four major steps:

### 1. Data Collection

Data are collected directly from:

* World Bank API
* IMF Fiscal Monitor API

### 2. Data Processing

* Country harmonization
* Missing value treatment
* Variable standardization
* Construction of a country-year panel dataset

### 3. Feature Engineering

Indicators are grouped into four dimensions:

#### Fiscal Sustainability

* Gross Debt (% GDP)
* Net Debt (% GDP)
* Fiscal Balance (% GDP)
* Primary Balance (% GDP)

#### Macroeconomic Stability

* GDP Growth
* Inflation
* Unemployment
* GDP per Capita

#### Demographic Pressure

* Population Aged 65+
* Fertility Rate
* Age Dependency Ratio

#### External Vulnerability

* Current Account Balance
* External Debt
* International Reserves

### 4. Fiscal Risk Index Construction

Alternative methodologies considered:

* Weighted Scorecard
* Principal Component Analysis (PCA)
* Z-Score Aggregation

The final index is normalized between:

* 0 = Lowest Fiscal Risk
* 100 = Highest Fiscal Risk

## Repository Structure

```text
fiscal-risk-index/

├── data/
│   ├── raw/
│   └── processed/
│
├── notebooks/
│
├── src/
│   ├── download_wdi.py
│   ├── download_imf.py
│   ├── build_panel.py
│   └── calculate_fiscal_risk_index.py
│
├── README.md
└── requirements.txt
```

## Technologies

* Python
* Pandas
* NumPy
* Scikit-Learn
* Requests
* World Bank API
* IMF SDMX API
* Streamlit

## Future Improvements

* Governance indicators (Worldwide Governance Indicators)
* Sovereign credit ratings
* Fiscal stress prediction models
* Machine learning classification of fiscal crises
* Interactive dashboard

## Author

João Victor Freitas

Economist | Data Scientist | Financial Risk Professional
