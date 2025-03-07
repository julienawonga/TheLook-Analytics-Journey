> [X] Évolution MoM du CA 
```sql
WITH ca_mensuel AS (
  SELECT
    FORMAT_DATE('%Y-%m', o.created_at) AS mois,
    ROUND(SUM(oi.sale_price), 2) AS ca
  FROM 
    `bigquery-public-data.thelook_ecommerce.orders` AS o
  JOIN 
    `bigquery-public-data.thelook_ecommerce.order_items` AS oi
    ON o.order_id = oi.order_id
  GROUP BY mois
),
evolution AS (
  SELECT
    mois,
    ca,
    LAG(ca) OVER(ORDER BY mois) AS ca_mois_precedent,
    ROUND(100 * (ca - LAG(ca) OVER(ORDER BY mois)) / LAG(ca) OVER(ORDER BY mois), 2) AS variation_mom_pct
  FROM ca_mensuel
)
SELECT *
FROM evolution
ORDER BY mois;

```
>  [X] Top 10 des produits les plus vendus
```sql
SELECT
  p.name AS produit,
  COUNT(*) AS nb_vendus
FROM 
  `bigquery-public-data.thelook_ecommerce.order_items` AS oi
JOIN 
  `bigquery-public-data.thelook_ecommerce.products` AS p
  ON oi.product_id = p.id
GROUP BY 
  p.name
ORDER BY 
  nb_vendus DESC
LIMIT 10;
```