# 📊 Rossmann Sales Forecasting  
### Магістерський проєкт з машинного навчання  
**Автор:** Volodymyr Chub  
**Рік:** 2025  

---

## 🧩 Опис проєкту

Цей проєкт присвячений прогнозуванню денних продажів у роздрібній мережі **Rossmann**  
за допомогою сучасних методів машинного навчання та інтерпретованих моделей.

Мета роботи — створити **точну, стабільну та зрозумілу систему прогнозування**,  
яку можна інтегрувати у реальні бізнес-процеси.

Розроблений ML-пайплайн охоплює:
- дослідження даних (EDA),
- інженерію ознак,
- очищення та масштабування,
- навчання та тюнінг моделей,
- ансамблювання,
- SHAP-інтерпретацію,
- розробку Streamlit-дашборду.

---

## 📁 Структура репозиторію



```
streamlit_app/
│
├── app.py # головний Streamlit-додаток
├── style.css # стилізація інтерфейсу
│
├── data/
│ ├── metrics.csv # метрики моделей
│ ├── model_results.csv # фактичні та прогнозні значення
│ ├── shap_values_summary.png
│
├── plots/
│ ├── eda_sales_distribution.png
│ ├── eda_promo_effect.png
│ ├── correlation_before.png
│ ├── actual_vs_predicted_catboost.png
│ ├── actual_vs_predicted_xgboost.png
│ ├── actual_vs_predicted_randomforest.png
│ ├── residuals_plot.png
│
└── pages/
├── 1_Overview.py
├── 2_EDA.py
├── 3_Feature_Engineering.py
├── 4_Models_Comparison.py
├── 5_Predictions.py
├── 6_Residuals.py
├── 7_SHAP_Explainability.py
└── 8_Conclusions.py
```

---

## 🔍 Дані

Використано датасет **Rossmann Store Sales** (Kaggle).  
Після попередньої обробки:

- ~1 000 000 рядків  
- період: 2013–2015  
- магазинні та промо-дані  
- таргет: `Sales`

---

## 🧱 ML-пайплайн

### 1️⃣ **EDA — дослідження даних**
- Розподіл продажів  
- Вплив промо-акцій  
- Кореляційна структура  

### 2️⃣ **Інженерія ознак**
- календарні ознаки  
- промо-фактори (`Promo`, `Promo2`, `PromoInterval`, `Promo2SinceWeek`)  
- конкуренція (`CompetitionDistance`, `CompetitionOpenSinceYear`)  
- видалення мультиколінеарності  
- StandardScaler для X та y  

### 3️⃣ **Моделі**
Використано 7 моделей:

- CatBoost (Base & Tuned)  
- XGBoost  
- RandomForest (Base & Tuned)  
- ElasticNet (допоміжна)  
- Weighted Ensemble  
- Stacked Ensemble  

### 4️⃣ **Тюнінг**
- GridSearchCV (RandomForest)  
- Optuna Bayesian Optimization (CatBoost)  

### 5️⃣ **Ансамблювання**
- Weighted Ensemble  
- Stacked Ensemble (GPU base + CPU meta)  

### 6️⃣ **SHAP Explainability**
- визначення найважливіших ознак  
- пояснення впливу конкурентів  
- оцінка ролі промо-кампаній і сезонності  

---

## 📈 Результати моделювання

### 🏆 Найкраща модель: **Stacked Ensemble**

| Метрика | Значення |
|--------|----------|
| MAE    | **0.207** |
| RMSE   | **0.301** |
| WAPE   | **0.0919** |
| MAPE   | **10.29%** |
| R²     | **0.91** |

### ⚡ Найкраще співвідношення швидкість / точність: **CatBoost (Tuned)**

- час виконання: **0.02 сек**
- майже така ж точність, як Stacked Ensemble  
- найкраще підходить для реального використання

### 📌 Додаткові інсайти:
- Promo2, SchoolHoliday, Weekend → вагомі сезонні й поведінкові фактори  
- CompetitionOpenSinceYear → найважливіша ознака згідно SHAP  
- правильна інженерія ознак підняла точність моделей на ~20%  

---

## 🖥️ Streamlit Dashboard

У проєкті реалізовано **повноцінний багатосторінковий Streamlit App**:

- лівий sticky-sidebar з іконками  
- окремі сторінки для EDA, FE, моделей, прогнозів  
- графіки Actual vs Predicted  
- аналіз залишків  
- SHAP-інтерпретація  
- кастомний дизайн (CSS)

---

## ▶️ Як запустити застосунок

### 1️⃣ Встановити залежності
```
pip install streamlit pandas numpy pillow catboost xgboost scikit-learn optuna shap
```
### 2️⃣ Запустити Streamlit-додаток:
```
streamlit run app.py
```
### 3️⃣ Відкрити в браузері:

http://localhost:8501
