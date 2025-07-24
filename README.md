
# 🏊‍♂️ Olympic Swimming Analysis & 2028 Gold‑Medal Time Prediction

This repository explores **112 years of Olympic swimming history (1912 → 2020)** and uses machine‑learning to forecast the **100 m freestyle gold‑medal time at the 2028 Los Angeles Games**.

---

## 📂 Project Layout

```text
.
├── data/
│   └── Olympic_Swimming.csv        # Cleaned event‑level dataset (1912‑2020)
├── Notebooks/
│   ├── eda_and_preprocessing.ipynb # Exploratory data analysis + feature prep
│   └── prediction_100m_gold_2028.ipynb # ML pipeline & 2028 prediction
├── models/                         # Saved model artefacts (ignored in Git)
├── outputs/                        # Figures & produced tables
├── requirements.txt
└── README.md                       # ← you are here
```

Large binaries (datasets, trained models) are excluded via `.gitignore`.

---

## ❓ Research Questions

1. **How have 100 m gold‑medal times evolved by stroke and gender since 1912?**  
2. **Which countries have dominated Olympic swimming, and how has dominance shifted over time?**  
3. **What will be the winning time in the men’s 100 m freestyle final at LA 2028?**

---

## 🔍 Key Insights (EDA)

| Theme | Highlight |
|-------|-----------|
| **Performance trend** | All four strokes show steady improvements; slope flattens after 2000 indicating physiological limits. |
| **Gender gap** | Average male–female gap ≈ 9 % across strokes; smallest in breaststroke, largest in butterfly. |
| **Nation dominance** | USA leads 🇺🇸 (> 40 % of golds), followed by Australia 🇦🇺 and historically East Germany 🇩🇪. |
| **Event growth** | Swimming medal events grew from 9 (1912) to 37 (2020), with parity in men/women events by 1996. |
| **Relay boost** | Relay split times are ≈ 2–3 % faster than equivalent individual swims. |

---

## 🛠️ Modelling Pipeline

| Step | Details |
|------|---------|
| **Split** | Train = 1912‑2016, Test = 2020 (hold‑out Games). |
| **Features** | `year`, `gender`, `stroke`, `event_distance`, 4‑cycle moving average, tech‑era dummy, etc. |
| **Pre‑processing** | StandardScaler for numeric, OneHotEncoder for categoricals (wrapped in `ColumnTransformer`). |
| **Model** | **LightGBM Regressor** (`objective='regression_l2'`, `metric='l2'`). |
| **Evaluation** | MSE on 2020 hold‑out = **0.637 s²**. |
| **Forecast** | Predicted 2028 100 m freestyle gold‑medal time = **48.06 s**. |

---

## 📊 Results Snapshot

```text
2020 actual (Tokyo):
  • Men  : 47.02 s
  • Women: 51.96 s

2028 prediction (LightGBM):
  • Men  : 48.06 s
```

> Interpretation: The model expects a slight regression versus the Tokyo WR‑level swim, reflecting plateauing improvements and post‑suit‑era trend.

---

## 🚀 Quick Start

```bash
# Clone the repo
git clone https://github.com/PrielDavid/olympic_swimming_analysis.git
cd olympic_swimming_analysis

# Create & activate environment
python -m venv venv
source venv/bin/activate        # On Windows: venv\Scripts\activate

# Install requirements
pip install -r requirements.txt

# Launch notebooks
jupyter lab Notebooks/eda_and_preprocessing.ipynb
```

---

## ♻️ Reproducibility

* Random seed fixed (`random_state=42`).
* End‑to‑end pipeline encapsulated in Scikit‑learn `Pipeline`.
* Models & encoders dumped via `joblib` in `/models`.
* Notebook cell execution order preserved.

---

## 🔮 Future Work

* Add **SHAP** explainability to quantify feature impacts.  
* Incorporate **FINA World Championship** data for richer trend estimation.  
* Hyper‑parameter optimisation with **Optuna**.  
* Deploy an interactive **Streamlit** dashboard for exploring trends and forecasts.

---

## 👤 Author

**Priel Davidpor** – Economics & Statistics BSc, Ben‑Gurion University  
Connect on [LinkedIn](https://www.linkedin.com/in/priel-davidpor/).

---

## 📄 License

Distributed under the MIT License — see `LICENSE` for details.
