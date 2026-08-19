# Детекция мошеннических операций по картам

Пет-проект на классическом Kaggle-датасете [Credit Card Fraud Detection](https://www.kaggle.com/datasets/mlg-ulb/creditcardfraud): транзакции держателей карт за два дня сентября 2013 года. Признаки `V1`–`V28` — выход PCA, плюс `Time`, `Amount` и целевая `Class`.

Задача — бинарная классификация из сильно дисбалансного датасета: из 284 807 транзакций мошеннических всего 492, то есть 0.17%. Поэтому смотреть надо на AUPRC и на precision/recall по классу фрода, а не на общую точность.

В ноутбуке я сравниваю два подхода к такой задаче: классический ML (Logistic Regression, KNN, Random Forest с балансировкой весов и подбором гиперпараметров) и небольшую нейросеть на TensorFlow. Спойлер: лес даёт precision 0.94 при recall 0.81, сеть — recall 0.84, но precision всего 0.71.

Один и тот же разбор лежит в двух версиях: [`ru_solution.ipynb`](ru_solution.ipynb) и [`en_solution.ipynb`](en_solution.ipynb).

## Как запустить

```bash
pip install pandas numpy scikit-learn matplotlib tensorflow jupyter
```

Датасет не лежит в репозитории, его можно скачать самостоятельно (~144 МБ) — [скачайте с Kaggle](https://www.kaggle.com/datasets/mlg-ulb/creditcardfraud) и положите `creditcard.csv` в корень проекта. Дальше `jupyter notebook ru_solution.ipynb`.
