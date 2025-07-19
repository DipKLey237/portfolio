# 🛍️ Online Retail II – Data Analysis Project

Ce projet est basé sur le dataset **Online Retail II** (2010–2011), disponible sur [Kaggle](https://www.kaggle.com/datasets/mashlyn/online-retail-ii-data-set).

L’objectif est de réaliser une analyse complète des ventes en ligne à travers une approche *end-to-end*, comprenant le nettoyage, l'exploration, l'analyse, et la visualisation des données avec Power BI.

---

## 📁 Dossier du projet


portfolio/
└── online_retail_ii/
    ├── data/
    ├── notebooks/
    ├── powerbi_visuals/
    │   ├── Customer_insight_dashboard.png
    │   └── Product_insight_dashboard.png
    └── README.md

---

## 📊 Objectifs de l'analyse

1. **Comprendre le comportement des clients.**
2. **Identifier les produits les plus performants.**
3. **Analyser la répartition géographique des ventes.**
4. **Suivre les tendances mensuelles de chiffre d'affaires.**


---

## 🔍 Étapes du projet

1. **Importation et nettoyage des données**  (Python – `pandas`)
    - Traitement des valeurs manquantes
    - Formatages des dates et montants
    - Suppression des retour et doublons 

2. **Analyse exploratoire**  (`pandas`,`seaborn`)
    - Traitement des valeurs manquantes
    - Analyse des clients, pays, produits, commandes
    - Création d'indicateurs agrégés

3. **Visualisation interactive (Power BI)**
    - Création dashboard dynamique
    - Export des dashboards sous forme de capture d'écran

---

## 📈 Dashboards Power BI

###  1️⃣ Customer Insight Dashboard

![Customer Insight](powerbi_visuals/Customer_insight_dashboard.png)

- **Nombre de clients** : 4 338
- **Chiffre d’affaires total** : 8,91 M
- **Répartition géographique des ventes**: (carte)
- **Revenu par pays et par client**
- **Tendances mensuelles des ventes**


### 2️⃣ Product Insight Dashboard

![Product Insight](powerbi_visuals/Product_insight_dashboard.png)

- **Nombre total de produits** : 3 868
- **Top ventes par produit**: (en CA et en quantité)
- **Ventes par produit et par pays**: (carte)
- **Tendance mensuelle des quantités vendues**

---

### 🧠 Insights clés
- **Le Royaume-Uni** génère l’essentiel des ventes.
- **Le produit "Manual"** domine à la fois en termes de revenus et de quantités.
- **Novembre et décembre** sont les mois les plus performants.
- **Une corrélation forte** existe entre volume de commandes et chiffre d'affaires.

---

## 🛠️ Outils utilisés
- Python (pandas, seaborn, matplotlib)
- Power BI (dashboards interactifs)
- Visual Studio Code

---

## 🔗 Ressources
- [Dataset Kaggle](https://www.kaggle.com/datasets/mashlyn/online-retail-ii-data-set)
- [Documentation pandas](https://pandas.pydata.org/docs/)
- [Power BI Docs](https://learn.microsoft.com/fr-fr/power-bi/)

---

## ✍️ Auteur

**Oliver NGANGUE** – Formation Data Analyst @ Artefact School of Data
Ce projet s’inscrit dans mon portfolio professionnel pour postuler à des rôles de Data Analyst Junior.