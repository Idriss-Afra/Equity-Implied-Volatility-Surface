# Equity Implied Volatility Surface

A quantitative finance repository focused on extracting market-implied information from listed equity options.

This repo contains **two separate projects**:

1. **De-Americanization for Implied Dividends**  
   Recover discrete cash dividends from **American-style options**.

2. **Equity Implied Forward & Volatility Surface**  
   Build the implied forward curve, dividend yield curve, and volatility surface from **European-style options**.

---

## Repository Structure

```text
Equity-Implied-Volatility-Surface/
├── De-Americanization Algorithm.ipynb
├── Equity Implied Forward & Volatility Surface.ipynb
└── MarketData/
    ├── CAC40_MarketOptions_12022025.csv
    └── EURIBOR6M_ZCRates_12022025.csv
```

---

## Project 1 — De-Americanization for Implied Dividends

This notebook focuses on **American-style equity options**.

Because American options can be exercised early, their prices cannot be used directly with standard European parity relationships. To handle this, the notebook:

* models option prices with a **binomial tree**
* estimates the **early-exercise premium**
* converts American prices into **European-equivalent prices**
* extracts implied forwards and dividend information
* bootstraps **discrete cash dividends**

### Best use case

Use this notebook when working with **American options** and trying to recover **implied cash dividends** from market prices.

---

## Project 2 — Equity Implied Forward & Volatility Surface

This notebook focuses on **European-style equity options**.

Its goal is to extract market-implied information and construct:

* an **implied forward curve**
* an **implied dividend yield curve**
* an **implied volatility surface**

The workflow includes:

* forward extraction from market option prices
* dividend yield inference across expiries
* implied volatility calibration
* interpolation across strikes and maturities
* surface visualization

### Market Data

The `MarketData/` folder includes:

* `CAC40_MarketOptions_12022025.csv` — option market quotes
* `EURIBOR6M_ZCRates_12022025.csv` — zero-coupon rates for discounting

Users can replace the sample input files with their own market data, provided that the CSV files keep the same structure as the ones included in `MarketData/`.  
To run the notebook correctly, the current column layout and overall file format must be respected.

### Example Output

**CAC40 Dividend Yield Structure**:

<img width="500" height="500" alt="image" src="https://github.com/user-attachments/assets/7c73e97f-8871-463f-b508-0219c8b790f9" />

**CAC40 Implied Volatility Surface**:

<img width="500" height="500" alt="image" src="https://github.com/user-attachments/assets/cbf5912f-32c9-4a37-8c77-8e2747833f75" />

### Best use case

Use this notebook when working with **European options** and building a **forward-consistent volatility surface**.

---

## How to Use

Clone the repository:

```bash
git clone https://github.com/Idriss-Afra/Equity-Implied-Volatility-Surface.git
cd Equity-Implied-Volatility-Surface
jupyter notebook
```

Then open:

* `De-Americanization Algorithm.ipynb`
* `Equity Implied Forward & Volatility Surface.ipynb`

---

## Author

**Idriss Afra**
