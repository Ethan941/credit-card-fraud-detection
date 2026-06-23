# 💳 Credit Card Fraud Detection

Projet de **Data Science** autour de la détection de fraude bancaire à partir de données de transactions.

L’objectif est de construire un pipeline complet permettant de préparer les données, analyser les comportements de fraude, entraîner des modèles de Machine Learning et évaluer leurs performances avec des métriques adaptées au contexte bancaire.

---

## 🎯 Objectif du projet

Les fraudes bancaires représentent un risque important pour les institutions financières.

Ce projet cherche à répondre à une problématique métier simple :

> Comment détecter automatiquement les transactions frauduleuses tout en limitant les faux positifs ?

Dans ce contexte, le modèle doit être capable de repérer un maximum de fraudes, même lorsque celles-ci représentent une très faible proportion des transactions.

---

## 🧠 Problématique Data Science

La détection de fraude est un problème de classification binaire :

- `0` : transaction normale
- `1` : transaction frauduleuse

Le principal défi est le déséquilibre des classes : les fraudes sont rares par rapport aux transactions normales.

---

## 🛠️ Technologies utilisées

- Python
- Pandas
- NumPy
- Scikit-learn
- Matplotlib
- Seaborn
- Jupyter Notebook

---

## 📁 Structure du projet

```txt
credit-card-fraud-detection/
│
├── data/
│   └── raw/                 # Données brutes
│
├── notebooks/               # Analyse exploratoire et entraînement des modèles
│
├── models/                  # Modèles entraînés
│
├── reports/
│   └── figures/             # Graphiques et visualisations
│
├── README.md
└── .gitignore
