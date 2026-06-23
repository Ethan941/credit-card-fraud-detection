# 💳 Credit Card Fraud Detection

Projet de **Data Science** appliqué à la détection de fraude bancaire.

L’objectif est de construire un modèle de Machine Learning capable d’identifier les transactions frauduleuses à partir de données de transactions.

Ce projet met en avant un workflow complet : chargement des données, analyse exploratoire, préparation, modélisation, évaluation et interprétation des résultats.

---

## 🎯 Objectif du projet

La fraude bancaire est un problème majeur pour les banques, les fintechs et les entreprises de paiement.

Les transactions frauduleuses sont généralement rares, mais leur impact financier peut être important.

Ce projet cherche à répondre à la question suivante :

> Comment détecter automatiquement les transactions frauduleuses à partir de données historiques ?

L’objectif est de développer un modèle capable de repérer un maximum de fraudes tout en limitant les faux positifs.

---

## 🧠 Problématique Data Science

Il s’agit d’un problème de **classification binaire**.

La variable cible indique si une transaction est frauduleuse ou non :

| Valeur | Signification |
|---|---|
| `0` | Transaction normale |
| `1` | Transaction frauduleuse |

La principale difficulté est le **déséquilibre des classes** : les fraudes représentent une très petite partie des transactions.

Dans ce contexte, l’accuracy seule n’est pas suffisante. Un modèle peut obtenir une très bonne accuracy en prédisant presque toutes les transactions comme normales, tout en ratant les fraudes.

---

## 📊 Données utilisées

Le dataset contient des transactions bancaires anonymisées.

Exemples de variables :

| Variable | Description |
|---|---|
| `Time` | Temps écoulé depuis la première transaction |
| `V1` à `V28` | Variables anonymisées issues d’une transformation PCA |
| `Amount` | Montant de la transaction |
| `Class` | Variable cible : 0 normale, 1 fraude |

---

## 🛠️ Technologies utilisées

- Python
- Pandas
- NumPy
- Matplotlib
- Seaborn
- Scikit-learn
- Jupyter Notebook
- Git / GitHub

---

## 📁 Structure du projet

```txt
credit-card-fraud-detection/
│
├── data/
│   ├── raw/
│   │   └── creditcard.csv
│   │
│   └── processed/
│       └── creditcard_clean.csv
│
├── notebooks/
│   ├── 01_eda.ipynb
│   ├── 02_modeling.ipynb
│   └── 03_evaluation.ipynb
│
├── models/
│   └── best_model.pkl
│
├── reports/
│   ├── figures/
│   │   ├── class_distribution.png
│   │   ├── confusion_matrix.png
│   │   └── roc_curve.png
│   │
│   └── fraud_detection_report.pdf
│
├── src/
│   ├── data_preprocessing.py
│   ├── train_model.py
│   └── evaluate_model.py
│
├── requirements.txt
├── README.md
└── .gitignore
```

---

## 🔎 Méthodologie

### 1. Chargement des données

La première étape consiste à charger le dataset et à vérifier sa structure.

Contrôles réalisés :

- nombre de lignes ;
- nombre de colonnes ;
- types de variables ;
- valeurs manquantes ;
- doublons ;
- distribution de la variable cible.

---

### 2. Analyse exploratoire

L’analyse exploratoire permet de mieux comprendre les transactions.

Analyses réalisées :

- distribution des transactions normales et frauduleuses ;
- analyse du déséquilibre des classes ;
- distribution des montants ;
- comparaison des montants entre fraudes et transactions normales ;
- analyse de la variable `Time` ;
- visualisation des tendances principales ;
- corrélations entre variables.

---

### 3. Préparation des données

Étapes possibles :

- séparation des variables explicatives et de la cible ;
- séparation train/test ;
- standardisation de `Amount` ;
- standardisation de `Time` si nécessaire ;
- gestion du déséquilibre des classes ;
- préparation des données pour les modèles.

---

## ⚖️ Gestion du déséquilibre des classes

La fraude bancaire est un cas typique de dataset déséquilibré.

Problème :

```txt
Transactions normales : très nombreuses
Transactions frauduleuses : très rares
```

Conséquence :

- l’accuracy peut être trompeuse ;
- le recall devient une métrique importante ;
- la matrice de confusion est indispensable ;
- les faux négatifs sont coûteux.

Approches possibles :

- utiliser `class_weight='balanced'` ;
- tester le sous-échantillonnage ;
- tester le sur-échantillonnage ;
- tester SMOTE ;
- comparer plusieurs métriques.

---

## 🤖 Modélisation

Modèles utilisés ou prévus :

### Logistic Regression

Modèle simple, rapide et interprétable.

Avantages :

- facile à entraîner ;
- bonne baseline ;
- interprétable ;
- efficace pour commencer.

### Random Forest

Modèle plus robuste capable de capturer des relations non linéaires.

Avantages :

- performant sur de nombreux problèmes ;
- gère mieux les interactions entre variables ;
- permet d’obtenir l’importance des variables.

### Améliorations futures

- XGBoost ;
- LightGBM ;
- Isolation Forest ;
- AutoEncoder ;
- modèles de détection d’anomalies.

---

## 📏 Évaluation des modèles

Les métriques utilisées sont :

| Métrique | Rôle |
|---|---|
| Accuracy | Taux global de bonnes prédictions |
| Precision | Fiabilité des alertes de fraude |
| Recall | Capacité à détecter les fraudes réelles |
| F1-score | Équilibre entre precision et recall |
| ROC-AUC | Capacité à séparer les classes |
| Matrice de confusion | Visualisation des bonnes et mauvaises prédictions |

Dans un contexte de fraude, le **recall** est très important, car un faux négatif signifie qu’une fraude n’a pas été détectée.

---

## 📊 Résultats des modèles

À compléter avec tes vrais résultats.

| Modèle | Accuracy | Precision | Recall | F1-score | ROC-AUC |
|---|---:|---:|---:|---:|---:|
| Logistic Regression | À compléter | À compléter | À compléter | À compléter | À compléter |
| Random Forest | À compléter | À compléter | À compléter | À compléter | À compléter |

---

## 📌 Matrice de confusion

À ajouter dans le dossier :

```txt
reports/figures/confusion_matrix.png
```

Puis afficher dans le README :

```md
![Matrice de confusion](reports/figures/confusion_matrix.png)
```

---

## 📈 Courbe ROC

À ajouter dans le dossier :

```txt
reports/figures/roc_curve.png
```

Puis afficher dans le README :

```md
![Courbe ROC](reports/figures/roc_curve.png)
```

---

## 🔍 Interprétation des résultats

L’analyse des résultats doit permettre de répondre à plusieurs questions :

- Le modèle détecte-t-il correctement les fraudes ?
- Le nombre de faux négatifs est-il acceptable ?
- Le modèle génère-t-il trop de faux positifs ?
- Quelle métrique est la plus importante dans ce contexte ?
- Le modèle est-il utilisable dans un contexte métier ?

---

## 💼 Lecture métier

Dans un contexte bancaire, les erreurs n’ont pas toutes le même coût.

| Type d’erreur | Signification | Impact |
|---|---|---|
| Faux positif | Transaction normale détectée comme fraude | Peut gêner le client |
| Faux négatif | Fraude non détectée | Peut créer une perte financière |

L’objectif est donc de trouver un équilibre entre la détection maximale des fraudes et la limitation des alertes inutiles.

---

## ✅ Compétences démontrées

Ce projet montre des compétences en :

- Data Science ;
- Machine Learning supervisé ;
- classification binaire ;
- traitement d’un dataset déséquilibré ;
- analyse exploratoire ;
- préparation de données ;
- entraînement de modèles ;
- évaluation de modèles ;
- interprétation des résultats ;
- raisonnement métier autour des métriques.

---

## ⚙️ Installation

### 1. Cloner le repository

```bash
git clone https://github.com/Ethan941/credit-card-fraud-detection.git
cd credit-card-fraud-detection
```

### 2. Créer un environnement virtuel

```bash
python -m venv .venv
```

Sur macOS / Linux :

```bash
source .venv/bin/activate
```

Sur Windows :

```bash
.venv\Scripts\activate
```

### 3. Installer les dépendances

```bash
pip install -r requirements.txt
```

### 4. Lancer Jupyter Notebook

```bash
jupyter notebook
```

Puis ouvrir les notebooks dans le dossier :

```txt
notebooks/
```

---

## ▶️ Utilisation

Exemple de workflow :

```bash
python src/data_preprocessing.py
python src/train_model.py
python src/evaluate_model.py
```

Si le projet est principalement en notebook :

```txt
1. Ouvrir 01_eda.ipynb
2. Lancer l’analyse exploratoire
3. Ouvrir 02_modeling.ipynb
4. Entraîner les modèles
5. Ouvrir 03_evaluation.ipynb
6. Analyser les résultats
```

---

## 🚀 Améliorations possibles

- Ajouter SMOTE ;
- tester XGBoost ou LightGBM ;
- optimiser les hyperparamètres ;
- sauvegarder le meilleur modèle avec Joblib ;
- créer une API FastAPI pour prédire une transaction ;
- créer une interface Streamlit ;
- ajouter des tests unitaires ;
- ajouter un rapport PDF final ;
- déployer une démonstration ;
- ajouter une analyse de coût métier des faux positifs et faux négatifs.

---

## 📌 Statut du projet

Projet Data Science en cours d’amélioration.

L’objectif est de construire une solution complète de détection de fraude bancaire, avec une approche technique et métier.

---

## 👤 Auteur

**Ethan Pandor**  
Étudiant en Bachelor Data & IA à HETIC  
Recherche stage ou alternance en Data Science / Data Engineering
