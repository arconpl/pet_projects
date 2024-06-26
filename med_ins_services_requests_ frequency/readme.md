## Предсказание активности пользователей услуг добровольного медицинского страхования
**Заказчик**: [MAINS Lab](https://mainslab.ai/)

### Описание задачи
- Доступны данные о количестве обращений за медицинской помощью по 50 000 застрахованным ДМС за 2022 год. 

Доступны 2 выборки: 

- `train` - выборка для обучения и валидации, 50 тыс. застрахованных с проставленными значениями `target`.
- `holdout` - выборка для тестирования качества модели Заказчиком. В этой выборке 10 000 застрахованных, значения `target` отсутствуют

Для оценки качества модели по требованию заказчика будет применяться метрика `MSE`.

**Задача:**
- На основании характеристик застрахованных и истории их обращений за 2022 год предсказать количество визитов за 2023 год.

## Использованный стек

- Python, Pandas, Numpy, Matplotlib, Seaborn, Scikit-learn, Imbalanced-learn, Catboost, PhiK, SHAP


## Лучшая модель
- `CatBoostRegressor` с гиперпараметрами:
    - `depth`: 3
    - `iterations`: 635
    - `learning_rate` = 0.0769,

## Полученная метрика
- на кросс-валидации `MSE`: **24.48**
- на выделенной из обучающей выборки тестовой выборке `MSE`: **23.75**
- на тестовой выборке заказчика (по информации от заказчика) `MSE`: **23.1**
