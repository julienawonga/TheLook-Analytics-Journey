```sql
    SELECT 
        min(age) AS min_age,
        max(age) AS max_age
    FROM `bigquery-public-data.thelook_ecommerce.users`
```


> [x] Répartition des clients par tranche d'âge
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
```sql
SELECT
    p.category,
    o.gender,
    COUNT(*) AS total_achats,
    ROUND(100 * COUNT(*) / SUM(COUNT(*)) OVER(PARTITION BY p.category),2) AS pourcentage
FROM `bigquery-public-data.thelook_ecommerce.orders` o
JOIN `bigquery-public-data.thelook_ecommerce.order_items` oi
    ON o.order_id = oi.order_id
JOIN `bigquery-public-data.thelook_ecommerce.products` p
    ON oi.product_id = p.id
GROUP BY 
    o.gender,
    p.category
ORDER BY 
    p.category
```
    
---

> [x] Clients ayant fait plus de 3 achats
```sql
WITH clients_fideles AS (
  SELECT
    user_id,
    COUNT(DISTINCT order_id) AS nb_achats
  FROM `bigquery-public-data.thelook_ecommerce.orders`
  GROUP BY user_id
  HAVING nb_achats > 3
)
SELECT
  cf.user_id,
  u.first_name,
  u.last_name,
  u.gender,
  cf.nb_achats
FROM clients_fideles cf
JOIN `bigquery-public-data.thelook_ecommerce.users` u
  ON cf.user_id = u.id
ORDER BY cf.nb_achats DESC;
```

---
> [X]  Panier moyen par ville

```sql
SELECT
  u.city,
  ROUND(SUM(oi.sale_price) / COUNT(DISTINCT o.order_id), 2) AS panier_moyen
FROM
  `bigquery-public-data.thelook_ecommerce.orders` AS o
JOIN `bigquery-public-data.thelook_ecommerce.order_items` AS oi
  ON o.order_id = oi.order_id
JOIN `bigquery-public-data.thelook_ecommerce.users` AS u
  ON o.user_id = u.id
GROUP BY
  u.city
ORDER BY
  panier_moyen DESC;
```