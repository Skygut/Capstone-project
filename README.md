# 📊 Rossmann Sales Forecasting — Магістерський проєкт

**Автор:** Volodymyr Chub  
**Програма:** Master of Science in Computer Science (Data Science & Data Analytics)  
**Рік:** 2025  

Цей репозиторій містить повний ML-проєкт з прогнозування денних продажів у мережі магазинів **Rossmann**.  
У проєкті поєднані машинне навчання, інженерія ознак, аналіз даних, ансамблеві моделі та інтерактивний Streamlit-додаток, створений спеціально для презентації результатів на захисті.

---

## 🧩 Опис проєкту

Метою роботи було створити **точну, стабільну та інтерпретовану модель**,  
яка прогнозує щоденні продажі магазинів Rossmann на основі:

- історичних даних продажів  
- промо-активності  
- календарних факторів  
- конкурентного середовища  

Модель та дашборд дозволяють:
- аналізувати дані,  
- вивчати вплив ознак,  
- порівнювати моделі,  
- оцінювати помилки прогнозу,  
- інтерпретувати результати через SHAP.

---

## 🧱 Стек технологій

- Python 3  
- Pandas, NumPy  
- Scikit-Learn  
- XGBoost  
- CatBoost  
- RandomForest  
- Optuna (Bayesian Optimization)  
- SHAP  
- Matplotlib, Seaborn  
- Streamlit  
- Kaggle API  

---

## 📁 Структура репозиторію

```
Capstone-project/
│
├── notebooks/
├── data/            
├── streamlit_app/        
│   ├── app.py
│   ├── style.css
│   ├── pages/
│   ├── plots/
│   ├── data/
│   └── README_STREAMLIT.md
│
├── README.md
└── LICENSE

```

---

## 🖥️ Streamlit Dashboard (Інтерактивний веб-додаток)

У репозиторії присутній окремий веб-додаток, який демонструє:

- EDA  
- створені ознаки  
- порівняння моделей  
- графіки *Actual vs Predicted*  
- аналіз залишків  
- SHAP-інтерпретацію  
- фінальні висновки  

Повний опис — у файлі  
👉 `streamlit_app/README_STREAMLIT.md`

### ▶️ Швидкий запуск Streamlit App

```bash
cd streamlit_app
pip install -r requirements.txt
streamlit run app.py

```

#### Після запуску:

http://localhost:8501
---

### Як запустити проєкт

### Клонувати репозиторій

```bash
git clone https://github.com/<your-username>/<your-repo>.git
cd <your-repo>
``` 
### Встановити залежності
якщо використовуєш Jupyter:
```
pip install notebook
```

### Налаштування Kaggle API

1. Зайдіть у профіль Kaggle → Account
2. Натисніть Create New Token
3. Збережіть файл kaggle.json
4. Перемістіть його:
```
mkdir ~/.kaggle
mv kaggle.json ~/.kaggle/
chmod 600 ~/.kaggle/kaggle.json
```
### Завантаження даних Rossmann

main.py автоматично завантажує датасети через Kaggle API.
Або вручну: 
```bash
kaggle competitions download -c rossmann-store-sales
unzip rossmann-store-sales.zip -d data/
```
Файли повинні бути такими:
```bash
data/train.csv
data/store.csv
```
### Запуск ноутбука
Відкрий ноутбук: ```jupyter notebook Capstone_Project_Rossmann_Sales_Forecasting.ipynb ```

або через VS Code:
Відкрити репозиторій у VS Code
дкрити файл main.ipynb
Запустити комірки по черзі

### Що робить ноутбук
В ``` Capstone_Project_Rossmann_Sales_Forecasting.ipynb ``` виконується:
- завантаження даних
- очищення та обробка пропусків
- створення ознак (feature engineering)
- тренування моделей:
  - RandomForest
  - XGBoost
  - CatBoost
- побудова ансамблю
- оцінка метрик
- генерація графіків
- виконання SHAP-аналізу


###  Результати

Створюються:

- порівняльна таблиця моделей
- ансамблева модель
- SHAP-аналіз
- графіки:
  - Actual vs Predicted
  - catter Plot
  - Feature Importance
  - SHAP Summary
Метрики:
- MAE
- RMSE
- WAPE
- MAPE
- R²

### Відтворення результатів
1. Встановити залежності
2. Завантажити дані
3. Запустити:

```bash
jupyter notebook Capstone_Project_Rossmann_Sales_Forecasting.ipynb
```
### Ліцензія
Проєкт розповсюджується під ліцензією MIT License.
