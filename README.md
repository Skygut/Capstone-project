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
### Запуск прогнозування
Запуск: ```python main.py ```
Скрипт виконує:
завантаження та об’єднання датасетів

очищення даних
feature engineering
тренування моделей ML
оптимізацію гіперпараметрів
створення ансамблю
оцінку метрик
побудову графіків
SHAP-аналіз важливості ознак

Результати зберігаються у папках:
```
results/metrics/
results/plots/
results/shap/
results/models/ 
```

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
python main.py
```
### Ліцензія
Проєкт розповсюджується під ліцензією MIT License.
