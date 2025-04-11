
Avant tout, j'ai verfier l'age minim et l'age maximun de mes utilisateur,
avec 

```sql
    SELECT 
        min(age),
        max(age)
    FROM `bigquery-public-data.thelook_ecommerce.users`
```


> [x] Répartition des clients par tranche d'âge
J'ai fait le classement en 4 catégories :

    1. Adolescents:
        12-17 ans

    2. Jeunes adultes:
        18-24 ans

    2. Adultes d'âge moyen:
        25-54 ans

    3. Seniors:
        55-70 ans

```sql
SELECT 
    CASE
        WHEN age BETWEEN 12 AND 18 THEN 'Adolescents'
        WHEN age BETWEEN 18 AND 24 THEN 'Jeunes adultes' 
        WHEN age BETWEEN 25 AND 54 THEN 'Adultes moyen' 
        WHEN age BETWEEN 55 AND 70 THEN 'Seniors'
    END AS tranche,
    COUNT(age) AS counts
FROM `bigquery-public-data.thelook_ecommerce.users`
GROUP BY 
    CASE
      WHEN age BETWEEN 12 AND 18 THEN 'Adolescents'
      WHEN age BETWEEN 18 AND 24 THEN 'Jeunes adultes' 
      WHEN age BETWEEN 25 AND 54 THEN 'Adultes moyen' 
      WHEN age BETWEEN 55 AND 70 THEN 'Seniors'
    END
ORDER BY counts DESC
```
---

> [x] Distribution des genres vs. catégories de produits achetés