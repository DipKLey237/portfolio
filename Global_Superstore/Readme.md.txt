# 📊 Dashboard Excel — Global Superstore (2014–2017)

**Projet portfolio – Olivier – 2025**  
Tableau de bord interactif construit sous **Microsoft Excel** à partir du dataset **Global Superstore**.  
Objectif : analyser les ventes par **catégorie, segment client, région et période**, avec des **KPI** clairs et des **filtres interactifs** (segments).

![Aperçu du dashboard](images/dashboard.png)

---

## ✨ Fonctionnalités

- **KPI principaux** : Ventes totales, Produits vendus (distincts), Commandes, Clients.
- **Filtres interactifs (segments)** : Année, Catégorie, Région, Segment client.
- **Graphiques** :
  - Ventes par catégories (barres horizontales)
  - “Profit” par segment client *(approximation basée sur les ventes – voir limites)*
  - Répartition géographique des ventes (graphique **Carte**)
  - Délais moyens de livraison par catégories
  - Évolution mensuelle des ventes (ordre calendrier : janv → déc)
- **Mise en page** avec tuiles KPI, bandeau titre, et stylisation homogène.

---

## 🗂️ Arborescence du dépôt



---

## 🧰 Outils & version

- **Excel Microsoft 365** (segments, carte, TCD “valeurs distinctes” via modèle de données).
- Power Query / Power Pivot **(optionnel)**.
- OS : Windows.

> Si vous n’avez pas `NB.UNIQUES()`, utilisez `SOMMEPROD(1/NB.SI(plage;plage))` pour compter les valeurs distinctes,  
> ou un **TCD** avec **Nombre de valeurs distinctes** (créer le TCD **en ajoutant au modèle de données**).

---

## 📈 KPIs & logiques (Excel)

- **Ventes totales** : `=SOMME(Tableau1[Sales])`
- **Clients uniques** :  
  - TCD → `Customer ID` en Valeurs → *Nombre de valeurs distinctes*, **ou**  
  - Formule : `=SOMMEPROD(1/NB.SI(Tableau1[Customer ID];Tableau1[Customer ID]))`
- **Produits distincts** : idem avec `Product Name`
- **Commandes** : `=NBVAL(Tableau1[Order ID])`
- **Panier moyen par commande (option)** : `=Ventes_totales / Nb_commandes`

> **Colonnes dérivées** utiles :
> - `Année` : `=ANNEE([@Order Date])`
> - `Mois` : `=TEXTE([@Order Date];"mmm")` + `NumMois` : `=MOIS([@Order Date])` (sert au tri calendrier)
> - `Délais livraison (jours)` : `=[@Ship Date]-[@Order Date]` (format Nombre)

---

## 🔄 Processus suivi (ETL léger)

1. **Exploration & cadrage** : choix du dataset *Global Superstore* (2014–2017).
2. **Nettoyage**  
   - Uniformisation des dates (`Order Date`, `Ship Date`)  
   - Correction des champs **Sales** en nombre (remplacement `.` → `,`)  
   - Doublons analysés (conservation des lignes correspondant à des commandes distinctes)  
   - Codes postaux manquants **conservés** pour ne pas perdre d’observations
3. **Dérivés** : `Année`, `Mois`, `NumMois`, `Délais livraison (jours)`, type client **B2B/B2C** (via `Segment`)
4. **Modélisation Excel** : TCD + segments (Année, Catégorie, Région, Segment)
5. **Visualisation** : KPI, barres, ligne temporelle, carte, délais moyens
6. **Mise en forme** : tuiles KPI, suppression du quadrillage, styles cohérents
7. **Export & publication** : PDF + README + dépôt GitHub

---

## ⚠️ Difficultés rencontrées & solutions

- **Sales au format texte** → `Ctrl+H` remplacer `.` par `,` puis conversion en nombre.  
- **TCD qui affiche 0 en Somme** → cause : chiffres en texte ; résolu après conversion.  
- **Segments** sans onglet “Outils de segment” visible → activer via *Fichier > Options > Personnaliser le ruban* et cliquer **dans** le segment pour voir l’onglet contextuel.  
- **Ordre des mois incohérent** → ajout `NumMois` et tri par ce champ.  
- **Carte peu lisible / plantages** → limiter le nombre d’éléments tracés, vérifier le champ géographique (State/Region), légende renommée.  
- **En-têtes de segments masqués** → réinitialisation via clic droit *Effacer le filtre du segment* (ou bouton/macro dédié).

---

## 🔬 Limites & choix méthodologiques

- Le dataset Kaggle ne contenait pas de **Profit** ni de **Cost** ; le visuel “Profit par segment” est une **approximation à partir des ventes** (à remplacer si vous disposez des marges réelles).
- Pas de colonne `Quantity` dans la version utilisée → pas de calcul “quantités vendues” réelles (l’indicateur “Produits vendus” est un **nombre de produits distincts**).
- La carte Excel reste moins interactive qu’un rapport Power BI. 

---

## 🚀 Pistes d’amélioration (Roadmap)

- Ajouter une estimation de **profit** (ex. marge % par catégorie).
- Créer une version **Power BI** interactive (tooltips, drill-through).
- Ajouter des **Top 10** (produits, clients) et **panier moyen**.
- Mettre en place un **bouton reset** des segments (macro VBA).

---

## ▶️ Comment utiliser le fichier

1. Ouvrez `Dashboard_Global_Superstore.xlsx`.  
2. Si nécessaire, **Actualisez** les TCD (Analyse du TCD > Actualiser).  
3. Utilisez les **segments** (Année, Catégorie, Région, Segment) pour filtrer.  
4. Pour l’ordre des mois : vérifiez que `NumMois` est bien dans l’axe du TCD (tri ascendant).

---

## 🔗 Données

- Source : *Global Superstore* (Kaggle)  
  https://www.kaggle.com/datasets/juhi1994/superstore  
- Période : 2014–2017  
- Licence : respectez la licence de la source (évitez de redistribuer les données si non autorisé).

---

## 👤 Auteur

**Olivier NGANGUE** — Projet portfolio (2025)  
N’hésitez pas à me contacter sur LinkedIn et à ⭐ le dépôt si ce projet vous a aidé.

---