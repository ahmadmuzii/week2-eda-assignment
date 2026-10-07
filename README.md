<p align="center">
  <img src="https://capsule-render.vercel.app/api?type=waving&color=0:0f172a,50:9a3412,100:fb923c&height=200&section=header&text=Used-Car%20Price%20EDA&fontSize=50&fontColor=ffffff&fontAlignY=36&animation=fadeIn&desc=Missing%20data%20%E2%80%A2%20imputation%20%E2%80%A2%20outliers&descSize=18&descAlignY=58" width="100%" alt="Used-Car EDA"/>
</p>

<p align="center">
  <img src="https://readme-typing-svg.demolab.com?font=Fira+Code&weight=600&size=19&duration=2400&pause=700&color=FB923C&center=true&vCenter=true&width=620&lines=MCAR%3F+MAR%3F+MNAR%3F+%F0%9F%A4%94;IQR+found+22+outliers.+Z-score+found+2.;Skewed+data+changes+the+answer." alt="typing"/>
</p>

<p align="center">
  <img src="https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white"/>
  <img src="https://img.shields.io/badge/Pandas-150458?style=for-the-badge&logo=pandas&logoColor=white"/>
  <img src="https://img.shields.io/badge/Seaborn-4C72B0?style=for-the-badge"/>
  <img src="https://img.shields.io/badge/SciPy-8CAAE6?style=for-the-badge&logo=scipy&logoColor=white"/>
  <a href="https://colab.research.google.com/github/ahmadmuzii/week2-eda-assignment/blob/main/Week%202%20EDA%20Assignment.ipynb"><img src="https://colab.research.google.com/assets/colab-badge.svg" height="28" alt="Open in Colab"/></a>
</p>

---

## 🧠 What I Did

Week 2 of a Data Science internship: a deeper EDA on a **CarDekho used-car dataset (1,234 cars × 13 columns, 1,083 missing values)** focused on *why* data is missing, how to fill it responsibly, and how outlier methods disagree on skewed data. **Individual assignment.**

```mermaid
flowchart LR
    A[Load & normalise<br/>column names] --> B[Diagnose missingness<br/>counts · % · heatmap]
    B --> C[Feature prep<br/>brand · vehicle_age<br/>parse mileage/engine/power units]
    C --> D[MCAR / MAR / MNAR<br/>reasoning]
    D --> E[Impute<br/>mode · group-wise median]
    E --> F[Outliers<br/>IQR vs Z-score]
    F --> G[Advanced EDA<br/>pivots · correlations · plots]
    G --> H[Memory optimisation<br/>downcast to float32]
```

## 🔍 Highlights

| Topic | What I found / did |
|---|---|
| **Missingness** | `new_price` is **85% missing**; `power` and `engine` also have gaps. Missingness varies by listing, so it's not purely random (MAR-style) |
| **Unit parsing** | Extracted numbers from strings like `"18.5 kmpl"`, `"1197 CC"`, `"82 bhp"` with regex |
| **Imputation** | `owner_type` → mode · `mileage` → median **within each fuel type**, so diesel and petrol cars aren't averaged together |
| **Outliers** | **IQR flagged 22** high prices, **Z-score only 2** — prices are right-skewed (kurtosis ≈ 429), which inflates the std and hides outliers from Z-score |
| **Business rule** | Expensive cars ≤ 5 years old are flagged `is_premium_outlier` and **kept** — they're likely genuine, not errors |
| **Insights** | Diesel cars sell for more than petrol; automatics cost more in most fuel types; price tracks power and engine size |
| **Part E — SQL research** | When to use SQL vs Pandas, `SELECT`, `JOIN`, `GROUP BY` |

Previous week: [Titanic EDA →](https://github.com/ahmadmuzii/week1-eda-assignment)

<p align="center">
  <img src="https://capsule-render.vercel.app/api?type=waving&color=0:fb923c,50:9a3412,100:0f172a&height=90&section=footer" width="100%" alt=""/>
</p>
