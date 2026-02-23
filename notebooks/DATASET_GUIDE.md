# Dataset Guide for Analytics Masterclass Notebooks

## Quick Setup

Create a `notebooks/` folder and place all `.ipynb` files there along with the required datasets.

```
notebooks/
├── Week01_KM_and_BGNBD.ipynb
├── Week02_Cox_PH_Model.ipynb
├── Week03_Churn_Segmentation.ipynb
├── Week04_Complete_CLV_Engine.ipynb
├── Week05_Competing_Risks.ipynb
├── Week06_WinBack_ROI.ipynb
├── Week07_Cohort_Economics.ipynb
├── Week08_Frailty_Models.ipynb
├── Week09_Switching_Costs.ipynb
├── Week10_Second_Purchase.ipynb
├── Week11_Model_Selection.ipynb
├── Week12_Reactivation_Windows.ipynb
├── Week13_Causal_Network.ipynb
├── WA_Fn-UseC_-Telco-Customer-Churn.csv    ← download once, used in Weeks 2,3,5,8,9
└── DATASET_GUIDE.md
```

---

## Dataset 1: CDNOW (No download needed)

**Used in:** Weeks 1, 4

**Source:** Bundled with the `lifetimes` Python library. Loads automatically via:
```python
from lifetimes.datasets import load_cdnow_summary, load_transaction_data
```

**Origin:** Fader, Hardie & Lee (2005). "Counting Your Customers the Easy Way: An Alternative to the Pareto/NBD Model." Marketing Science, 24(2), 275-284.

**Contents:** ~2,357 customers from an online CD store (late 1990s). Includes transaction dates and purchase amounts.

**No action required** — the notebooks handle loading automatically.

---

## Dataset 2: IBM Telco Customer Churn (Download once)

**Used in:** Weeks 2, 3 (and later Weeks 5, 8, 9)

**Source:** Kaggle  
**URL:** https://www.kaggle.com/datasets/blastchar/telco-customer-churn

**How to download:**
1. Go to the URL above (requires a free Kaggle account)
2. Click "Download" (you'll get a ZIP file)
3. Extract `WA_Fn-UseC_-Telco-Customer-Churn.csv`
4. Place it in the same folder as your notebooks

**Contents:** 7,043 telecom customers with:
- Demographics (gender, senior citizen, partner, dependents)
- Account info (tenure, contract type, payment method, monthly/total charges)
- Services (phone, internet type, streaming, tech support, online security)
- Churn status (Yes/No)

**Size:** ~955 KB

---

## Dataset 3: UCI Online Retail II (Optional, for advanced exercises)

**Used in:** Week 1 exercises, and later Weeks 7, 10, 12

**Source:** UCI Machine Learning Repository  
**URL:** https://archive.ics.uci.edu/dataset/502/online+retail+ii

**How to download:**
1. Go to the URL above
2. Click "Download"
3. Extract the Excel files
4. Place in notebooks folder

**Contents:** ~500K transactions from a UK-based online retailer (2009-2011). Includes invoice number, stock code, description, quantity, price, customer ID, and country.

**Size:** ~45 MB

**Note:** Weeks 1 and 4 notebooks work without this dataset (they use the bundled CDNOW data). This dataset is for deeper exploration and exercises.

---

## Dataset Mapping: Which Weeks Use What

| Weeks | Dataset | Notes |
|-------|---------|-------|
| 1, 4, 6, 7, 10, 11, 12 | **CDNOW** (auto-loads) | Transaction data bundled with `lifetimes` |
| 2, 3, 5, 8, 9 | **IBM Telco** (Kaggle download) | 7,043 telecom customers |
| 13 | **Simulated network** | Generated in-notebook, no download needed |
| Exercises (1, 7, 10) | **UCI Online Retail II** (optional) | For deeper exploration |

**Weeks 6, 12, 13** include synthetic extensions built on real datasets (win-back outcomes, reactivation events, customer networks). These are generated within the notebooks using documented random seeds for reproducibility.

---

## Python Environment

All notebooks require Python 3.8+ with the following packages:

```bash
pip install lifetimes lifelines pandas matplotlib seaborn scikit-learn networkx statsmodels
```

**Package versions tested:**
- lifetimes >= 0.11.3
- lifelines >= 0.27.0
- pandas >= 1.5.0
- scikit-learn >= 1.2.0
- matplotlib >= 3.6.0
- seaborn >= 0.12.0

---

## Running the Notebooks

**Option A: Google Colab (recommended for beginners)**
1. Upload the `.ipynb` file to Google Colab (colab.research.google.com)
2. Upload the Telco CSV when needed (or mount Google Drive)
3. Run cells top to bottom

**Option B: Jupyter locally**
```bash
pip install jupyterlab
jupyter lab
```

**Option C: VS Code**
Install the Jupyter extension for VS Code and open `.ipynb` files directly.
