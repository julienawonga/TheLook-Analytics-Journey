# **Schéma du Dataset TheLook Ecommerce**

Ce fichier décrit le schéma complet du dataset *TheLook Ecommerce* utilisé dans ce projet. Il inclut les tables, leurs colonnes, leurs types de données et leur rôle.

---

## **Tables et Colonnes**

### **distribution_centers**
| Colonne                  | Type             | Description                                   |
|--------------------------|------------------|-----------------------------------------------|
| id                       | INTEGER NULLABLE | Identifiant unique du centre de distribution |
| name                     | STRING NULLABLE  | Nom du centre de distribution                |
| latitude                 | FLOAT NULLABLE   | Latitude géographique                        |
| longitude                | FLOAT NULLABLE   | Longitude géographique                       |
| distribution_center_geom | GEOGRAPHY NULLABLE | Géométrie géographique                     |

### **events**
| Colonne          | Type             | Description                                   |
|------------------|------------------|-----------------------------------------------|
| id               | INTEGER NULLABLE | Identifiant unique de l'événement            |
| user_id          | INTEGER NULLABLE | Identifiant de l'utilisateur                 |
| sequence_number  | INTEGER NULLABLE | Numéro de séquence dans la session           |
| session_id       | STRING NULLABLE  | Identifiant de la session                    |
| created_at       | TIMESTAMP NULLABLE | Horodatage de l'événement                   |
| ip_address       | STRING NULLABLE  | Adresse IP                                   |
| city             | STRING NULLABLE  | Ville                                        |
| state            | STRING NULLABLE  | État/région                                  |
| postal_code      | STRING NULLABLE  | Code postal                                  |
| browser          | STRING NULLABLE  | Navigateur utilisé                           |
| traffic_source   | STRING NULLABLE  | Source de trafic                             |
| uri              | STRING NULLABLE  | URI de la page visitée                       |
| event_type       | STRING NULLABLE  | Type d'événement (view, add_to_cart, etc.)   |


### **inventory_items**
| Colonne                     | Type             | Description                                   |
|-----------------------------|------------------|-----------------------------------------------|
| id                          | INTEGER NULLABLE | Identifiant unique de l'item en stock        |
| product_id                  | INTEGER NULLABLE | Identifiant du produit associé               |
| created_at                  | TIMESTAMP NULLABLE | Date de création de l'item                 |
| sold_at                     | TIMESTAMP NULLABLE | Date de vente de l'item                    |
| cost                        | FLOAT NULLABLE   | Coût de l'item                              |
| product_category            | STRING NULLABLE  | Catégorie du produit                         |
| product_name                | STRING NULLABLE  | Nom du produit                              |
| product_brand               | STRING NULLABLE  | Marque du produit                           |
| product_retail_price        | FLOAT NULLABLE   | Prix de détail du produit                   |
| product_department          | STRING NULLABLE  | Département du produit                      |
| product_sku                 | STRING NULLABLE  | SKU (unité de gestion de stock) du produit  |
| product_distribution_center_id | INTEGER NULLABLE | Identifiant du centre de distribution      |

### **order_items**
| Colonne            | Type             | Description                                   |
|--------------------|------------------|-----------------------------------------------|
| id                 | INTEGER NULLABLE | Identifiant unique de l'élément de commande   |
| order_id           | INTEGER NULLABLE | Identifiant de la commande                    |
| user_id            | INTEGER NULLABLE | Identifiant de l'utilisateur                  |
| product_id         | INTEGER NULLABLE | Identifiant du produit                        |
| inventory_item_id  | INTEGER NULLABLE | Identifiant de l'item en stock                |
| status             | STRING NULLABLE  | Statut de l'élément de commande               |
| created_at         | TIMESTAMP NULLABLE | Date de création de l'élément               |
| shipped_at         | TIMESTAMP NULLABLE | Date d'expédition                           |
| delivered_at       | TIMESTAMP NULLABLE | Date de livraison                           |
| returned_at        | TIMESTAMP NULLABLE | Date de retour                              |
| sale_price         | FLOAT NULLABLE   | Prix de vente                                |


### **orders**
| Colonne          | Type             | Description                                   |
|------------------|------------------|-----------------------------------------------|
| order_id         | INTEGER NULLABLE | Identifiant unique de la commande            |
| user_id          | INTEGER NULLABLE | Identifiant de l'utilisateur                 |
| status           | STRING NULLABLE  | Statut de la commande (ex: pending, shipped) |
| gender           | STRING NULLABLE  | Genre de l'utilisateur                       |
| created_at       | TIMESTAMP NULLABLE | Date de création de la commande            |
| returned_at      | TIMESTAMP NULLABLE | Date de retour                             |
| shipped_at       | TIMESTAMP NULLABLE | Date d'expédition                          |
| delivered_at     | TIMESTAMP NULLABLE | Date de livraison                          |
| num_of_item      | INTEGER NULLABLE | Nombre d'items dans la commande              |

### **products**
| Colonne               | Type             | Description                                   |
|-----------------------|------------------|-----------------------------------------------|
| id                    | INTEGER NULLABLE | Identifiant unique du produit                |
| cost                  | FLOAT NULLABLE   | Coût du produit                              |
| category              | STRING NULLABLE  | Catégorie du produit                         |
| name                  | STRING NULLABLE  | Nom du produit                               |
| brand                 | STRING NULLABLE  | Marque du produit                            |
| retail_price          | FLOAT NULLABLE   | Prix de détail du produit                    |
| department            | STRING NULLABLE  | Département du produit                       |
| sku                   | STRING NULLABLE  | SKU (unité de gestion de stock) du produit   |
| distribution_center_id| INTEGER NULLABLE | Identifiant du centre de distribution        |

### **users**
| Colonne          | Type             | Description                                   |
|------------------|------------------|-----------------------------------------------|
| id               | INTEGER NULLABLE | Identifiant unique de l'utilisateur          |
| first_name       | STRING NULLABLE  | Prénom de l'utilisateur                      |
| last_name        | STRING NULLABLE  | Nom de famille de l'utilisateur              |
| email            | STRING NULLABLE  | Adresse email de l'utilisateur               |
| age              | INTEGER NULLABLE | Âge de l'utilisateur                         |
| gender           | STRING NULLABLE  | Genre de l'utilisateur                       |
| state            | STRING NULLABLE  | État/région de l'utilisateur                 |
| street_address   | STRING NULLABLE  | Adresse de l'utilisateur                     |
| postal_code      | STRING NULLABLE  | Code postal de l'utilisateur                 |
| city             | STRING NULLABLE  | Ville de l'utilisateur                       |
| country          | STRING NULLABLE  | Pays de l'utilisateur                        |
| latitude         | FLOAT NULLABLE   | Latitude géographique de l'utilisateur       |
| longitude        | FLOAT NULLABLE   | Longitude géographique de l'utilisateur      |
| traffic_source   | STRING NULLABLE  | Source de trafic de l'utilisateur            |
| created_at       | TIMESTAMP NULLABLE | Date de création du compte utilisateur     |
| user_geom        | GEOGRAPHY NULLABLE | Géométrie géographique de l'utilisateur    |