> [X] Stock par centre de distribution 
```sql
SELECT
  dc.name AS centre_distribution,
  COUNT(*) AS stock_actuel
FROM 
  `bigquery-public-data.thelook_ecommerce.inventory_items` AS ii
JOIN 
  `bigquery-public-data.thelook_ecommerce.distribution_centers` AS dc
  ON ii.product_distribution_center_id = dc.id
WHERE 
  ii.sold_at IS NULL
GROUP BY 
  dc.name
ORDER BY 
  stock_actuel DESC;
```

---
> [X] Produits en rupture
```sql
WITH stock_qte AS(
  SELECT
    product_id,
    count(*) AS qte_non_vendu
  FROM
    `bigquery-public-data.thelook_ecommerce.inventory_items`
  WHERE
      sold_at IS NULL
  GROUP BY product_id
)
SELECT
  p.name
FROM
  `bigquery-public-data.thelook_ecommerce.products` AS p
LEFT JOIN stock_qte AS sq
ON
  p.id = sq.product_id
WHERE 
  sq.product_id IS NULL

```