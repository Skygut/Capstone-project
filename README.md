# Rossmann Sales Forecasting — Capstone Project

Цей проєкт створений у межах моєї магістерської роботи і присвячений прогнозуванню щоденних продажів у мережі магазинів **Rossmann**.  
Скрипт використовує історичні дані, інформацію про магазини та промо-активність, створює нові ознаки, тренує моделі машинного навчання та формує точний прогноз продажів.

---

## Стек технологій

- Python 3  
- Pandas, NumPy  
- Scikit-Learn  
- XGBoost  
- CatBoost  
- RandomForest  
- Optuna (Bayesian Optimization)  
- SHAP  
- Matplotlib, Seaborn  
- Kaggle API  

---

## Структура репозиторію

```
project/
│
├── data/ # Датасети (після завантаження)
├── main.ipynb 
└──README.md
```
---

## Як запустити проєкт

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
```
kaggle competitions download -c rossmann-store-sales
unzip rossmann-store-sales.zip -d data/
```
Файли повинні бути такими:
```
data/train.csv
data/store.csv
```
### Запуск ноутбука
Відкрий ноутбук: ```jupyter notebook main.ipynb ```

або через VS Code:
Відкрити репозиторій у VS Code
дкрити файл main.ipynb
Запустити комірки по черзі

### Що робить ноутбук
В ``` main.ipynb ``` виконується:
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
```
jupyter notebook main.ipynb
```
### Ліцензія
Проєкт розповсюджується під ліцензією MIT License.
