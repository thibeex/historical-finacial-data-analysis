# 📈 S&P 500 Historical Financial Data Analysis

![Dashboard](Screenshot%202026-03-01%20111448.png)

> **A comprehensive financial data analysis and interactive dashboard built with R and Power BI, exploring nearly 100 years of S&P 500 market history.**

---

## 📌 Project Overview

This project performs end-to-end financial data analysis on the S&P 500 (^GSPC) historical stock price dataset, covering **24,654 trading days from 1927 to 2026**. The analysis pipeline combines **R for data preprocessing and feature engineering** with **Power BI for interactive dashboard visualization**.

---

## 🛠️ Tools & Technologies

| Tool | Purpose |
|------|---------|
| **R** | Data cleaning, preprocessing, feature engineering |
| **tidyverse** | Data manipulation and static visualizations |
| **lubridate** | Date parsing and time feature extraction |
| **zoo** | Rolling averages and window calculations |
| **ggplot2** | Static exploratory plots |
| **Power BI** | Interactive dashboard and KPI visualization |
| **DAX** | Custom measures and time intelligence calculations |

---

## 📂 Repository Structure

```
📁 historical-financial-data-analysis/
│
├── 📄 financial_dashboard_preprocessing.R  ← R preprocessing script
├── 📄 StockData.csv                         ← Clean daily stock data
├── 📄 MonthlySummary.csv                    ← Monthly aggregated data
├── 📄 YearlySummary.csv                     ← Yearly KPI summary
├── 📄 historical financial analysis.pbix    ← Power BI dashboard file
├── 🖼️  Screenshot 2026-03-01 111448.png     ← Dashboard preview
├── 🖼️  plot_price_ma.png                    ← Price & moving averages
├── 🖼️  plot_daily_returns.png               ← Daily return distribution
├── 🖼️  plot_volatility.png                  ← 30-day rolling volatility
├── 🖼️  plot_monthly_avg.png                 ← Monthly average prices
├── 🖼️  plot_cumulative_return.png           ← Cumulative return chart
└── 📄 README.md                             ← Project documentation
```

---

## 📊 Dataset

| Attribute | Details |
|-----------|---------|
| **Source** | [Kaggle — S&P 500 (^GSPC) Historical Data](https://www.kaggle.com/datasets/paveljurke/s-and-p-500-gspc-historical-data) |
| **Records** | 24,654 trading days |
| **Date Range** | December 1927 — February 2026 |
| **Columns** | Date, Open, High, Low, Close, Volume |

---

## ⚙️ R Preprocessing Pipeline

### Step 1 — Data Import & Validation
- Loaded raw CSV with 24,654 rows
- Validated column types, checked for missing values and duplicates
- Confirmed Date column parsed correctly as date type

### Step 2 — Date Feature Extraction
Extracted the following time features from the Date column:
- Year, Month, Month Number, Quarter (Q1–Q4)
- ISO Week Number, Weekday, Year-Month label

### Step 3 — Feature Engineering
Created the following financial metrics:

| Feature | Formula |
|---------|---------|
| Daily Change | Close − Open |
| Daily Return % | (Close − Open) / Open × 100 |
| Daily Range | High − Low |
| 7-Day MA | 7-day rolling mean of Close |
| 30-Day MA | 30-day rolling mean of Close |
| 90-Day MA | 90-day rolling mean of Close |
| 200-Day MA | 200-day rolling mean of Close |
| Volatility (30-day) | Rolling std dev of Daily Return % |
| Volume MA (30-day) | 30-day rolling mean of Volume |
| Cumulative Return % | (Close / First Close − 1) × 100 |
| Signal | Bullish / Bearish based on 200-Day MA |

### Step 4 — Data Export
Exported 3 optimized CSV files for Power BI:
- `StockData.csv` — full daily data with all engineered features
- `YearlySummary.csv` — one row per year for KPI cards
- `MonthlySummary.csv` — one row per month for trend analysis

---

## 🖥️ Power BI Dashboard

### KPI Cards
| Metric | Value |
|--------|-------|
| All Time High | 7,002 |
| All Time Low | 4.40 |
| Total Trading Days | 24,654 |
| Latest Date | 25/02/2026 |
| YTD Return % | 220% |
| Avg Daily Return | 0.0156% |

### Dashboard Visuals
1. **S&P 500 Price & Moving Averages** — Close price with 30, 90 and 200-day MA overlays
2. **Cumulative Return Since 1927** — Total growth from baseline (hero visual)
3. **Daily Return % Over Time** — Market volatility and performance consistency
4. **30-Day Rolling Volatility** — Risk periods and market uncertainty
5. **Average Monthly Trading Volume** — Buying/selling activity by month
6. **Average Closing Price by Month** — Seasonal price patterns
7. **Yearly Performance Summary Table** — Year-by-year breakdown with conditional formatting

### Interactive Filters
- **Year Slicer** — Filter by specific year(s)
- **Quarter Slicer** — Filter by Q1, Q2, Q3, Q4
- **Signal Slicer** — Filter by Bullish / Bearish / No Signal

---

## 📉 Key Findings

- The S&P 500 has delivered a **cumulative return of over 39,000%** since 1927
- **Highest volatility periods:** 1929 Great Depression, 2008 Financial Crisis, 2020 COVID-19
- **Best performing decade:** 1990s — driven by the dot-com boom
- **Average daily return:** 0.0156% — modest but compounding significantly over decades
- **Bullish signal dominates** recent years with Close consistently above the 200-day MA

---

## 🚀 How to Run

### R Preprocessing
```r
# 1. Set your working directory
setwd("path/to/your/folder")

# 2. Place sap500.csv in the working directory

# 3. Run the preprocessing script
source("financial_dashboard_preprocessing.R")

# Output: StockData.csv, MonthlySummary.csv, YearlySummary.csv
```

### Power BI Dashboard
```
1. Open Power BI Desktop
2. Open: historical financial analysis.pbix
3. If data doesn't load → Transform Data → update file paths
4. Click Refresh to reload data
```

---

## 👤 Author

**Olusanya Oluwatobi**
- GitHub: [@thibeex](https://github.com/thibeex)

---

## 📄 License

This project is open source and available under the [MIT License](LICENSE).

---

*Part of a 3-project Data Analytics Portfolio — Customer Segmentation (R) | Sentiment Analysis (R) | Financial Dashboard (R + Power BI)*
