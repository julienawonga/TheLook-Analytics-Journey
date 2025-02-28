## **Niveau 1 : Exploration & Analyses de Base (Jours 1 à 3)**

### **Jour 1 – Découverte des Clients**

**Tables :** `users`, `orders`
**Concepts SQL :** `GROUP BY`, `CASE`, `COUNT()`, `AVG()`, `JOINS`

- [X] Répartition des clients par tranche d'âge 
- [X] Distribution des genres vs. catégories de produits achetés 
- [X] Clients ayant fait plus de 3 achats 
- [ ] Densité des commandes par ville 
- [X] Panier moyen par ville 
- [ ] Taux de conversion par source de trafic 

### **Jour 2 – Analyse des Commandes et Ventes**

**Tables :** `orders`, `order_items`, `products`
**Concepts SQL :** `JOIN`, `WINDOW FUNCTIONS (RANK, DENSE_RANK)`, `DATE_TRUNC`, `COUNT()`, `SUM()`

- [X] Évolution MoM du CA 
- [X] Top 10 des produits les plus vendus 
- [ ] Taux de conversion par source de trafic 
- [ ] Distance moyenne entre clients et centres de distribution 
- [ ] Comparaison mobile vs. desktop 
- [ ] Répartition des heures d'achat 
- [ ] Top 5 jours avec pics de trafic 

### **Jour 3 – Exploration du Stock et des Centres de Distribution**

**Tables :** `inventory_items`, `distribution_centers`, `products`
**Concepts SQL :** `JOIN`, `SUM()`, `AVG()`, `GEOGRAPHY FUNCTIONS`, `CASE`

- [X] Stock par centre de distribution 
- [X] Produits en rupture 
- [ ] Coût total du stock par catégorie 
- [ ] Approvisionnement optimal par région 
- [ ] Clients dans un rayon de 50km d'un centre 
- [ ] Impact de la localisation sur les délais 
- [ ] Distance moyenne entre clients et centres de distribution 

---

## **Niveau 2 : Analyses Avancées (Jours 4 à 7)**

### **Jour 4 – Comportement et Fidélisation Client**

**Tables :** `orders`, `order_items`, `users`
**Concepts SQL :** `WINDOW FUNCTIONS (LAG, LEAD)`, `CASE`, `GROUPING SETS`, `COUNT()`, `DATE_DIFF()`

- [ ] Délai moyen entre commandes 
- [ ] Valeur des paniers par segment RFM 
- [ ] Segmentation en 5 groupes par valeur client 
- [ ] Taux de réachat par trimestre 
- [ ] Analyse des churners 
- [ ] Cohort mensuelle de rétention 
- [ ] Durée de vie moyenne des clients 

### **Jour 5 – Impact des Promotions et Campagnes Marketing**

**Tables :** `order_items`, `events`, `products`
**Concepts SQL :** `CASE`, `WINDOW FUNCTIONS`, `STRING_AGG()`, `CUBE`

- [ ] Impact des campagnes marketing 
- [ ] Funnel de conversion 
- [ ] Taux d'abandon par étape 
- [ ] Pages les plus visitées avant achat 
- [ ] Impact des retours sur la marge 
- [ ] Produits souvent achetés ensemble 
- [ ] Représentation textuelle des paniers ⚠️ (via `STRING_AGG()`) 

### **Jour 6 – Analyse Géographique & Logistique**

**Tables :** `distribution_centers`, `inventory_items`, `orders`, `users`
**Concepts SQL :** `GEOGRAPHY FUNCTIONS`, `PERCENTILE_CONT()`, `WINDOW FUNCTIONS`, `COUNT()`, `GROUP BY`

- [ ] Impact de la localisation sur les délais 
- [ ] Cartographie des zones sous-développées 
- [ ] Distance moyenne entre clients et centres de distribution 
- [ ] Percentile 90 des délais de livraison 
- [ ] Produits souvent achetés ensemble 
- [ ] Combinaisons de catégories les plus fréquentes 
- [ ] Densité des commandes par ville 

### **Jour 7 – Performance des Produits & Tendances d’Inventaire**

**Tables :** `inventory_items`, `order_items`, `products`
**Concepts SQL :** `ABC ANALYSIS`, `WINDOW FUNCTIONS`, `CASE`, `JOIN`

- [ ] Analyse ABC des produits 
- [ ] Marge par produit 
- [ ] Profitabilité par catégorie 
- [ ] Évolution des ventes par département de produit 
- [ ] Performance des produits en fonction des promotions 
- [ ] Analyse du taux de retour et son impact sur la marge 
- [ ] Chiffre d’affaires par produit, région et période 

---

## **Niveau 3 : Insights Complexes & Recommandations Business (Jours 8 à 10)**

### **Jour 8 – Analyse Multi-Dimensionnelle des Ventes**

**Tables :** `orders`, `order_items`, `products`
**Concepts SQL :** `CUBE`, `ROLLUP`, `WINDOW FUNCTIONS`, `SEGMENTATION`

- [ ] Marges et rentabilité des catégories 
- [ ] Impact des recommandations produit sur les ventes 
- [ ] Analyse des churners (approfondissement) 
- [ ] Segmentation des clients en fonction des comportements d’achat 
- [ ] Identification des clients à fort potentiel 

### **Jour 9 – Analyse Avancée des Clients et Segmentation**

**Tables :** `users`, `orders`, `order_items`
**Concepts SQL :** `COHORT ANALYSIS`, `K-MEANS SEGMENTATION`, `RFM ANALYSIS`

- [ ] Cohort mensuelle de rétention (approfondissement) 
- [ ] Durée de vie moyenne des clients 
- [ ] Taux de réachat par trimestre (approfondissement) 
- [ ] Performance des produits en fonction des promotions (approfondissement) 
- [ ] Recommandations stratégiques basées sur les insights client 

### **Jour 10 – Rapport Final & Recommandations Stratégiques**

**Tables :** Toutes
**Concepts SQL :** `KPI DASHBOARDS`, `FINAL REPORTING`

- [ ] Synthèse des insights globaux 
- [ ] Recommandations pour améliorer l’expérience client 
- [ ] Actions stratégiques pour booster les ventes 
- [ ] Analyse des leviers de croissance 
- [ ] Présentation des KPI clés et des pistes d’amélioration 

---

**Bonus : Exploration des Métadonnées et Utilisation du Framework BigFunction**
