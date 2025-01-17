Exercices depuis:
https://sql.sh/exercices-sql/commandes

1. Obtenir l’utilisateur ayant le prénom “Muriel” et le mot de passe “test11”, sachant que l’encodage du mot de passe est effectué avec l’algorithme Sha1.

```
SELECT * FROM `client` 
WHERE prenom='Muriel'
AND password=SHA('test11');
```

2. Obtenir la liste de tous les produits qui sont présent sur plusieurs commandes.

```
SELECT commande_ligne.nom, COUNT(commande_ligne.nom)
FROM commande_ligne
GROUP BY commande_ligne.nom
HAVING COUNT(commande_ligne.nom)>1
ORDER BY commande_id;
```

3. Obtenir la liste de tous les produits qui sont présent sur plusieurs commandes et y ajouter une colonne qui liste les identifiants des commandes associées.

```
SELECT commande_ligne.nom, COUNT(commande_ligne.nom), GROUP_CONCAT(commande_id)
FROM commande_ligne
GROUP BY commande_ligne.nom
HAVING COUNT(commande_ligne.nom)>1;
```

4. Enregistrer le prix total à l’intérieur de chaque ligne des commandes, en fonction du prix unitaire et de la quantité
```
UPDATE commande_ligne
SET prix_total=prix_unitaire*quantite;
```

5. Obtenir le montant total pour chaque commande et y voir facilement la date associée à cette commande ainsi que le prénom et nom du client associé

```
SELECT c.id, client.nom, client.prenom, SUM(prix_total)
FROM commande c
LEFT JOIN commande_ligne cl ON c.id=cl.commande_id
LEFT JOIN client ON c.client_id=client.id
GROUP BY c.id;
```

6. Enregistrer le montant total de chaque commande dans le champ intitulé “cache_prix_total”

```
UPDATE commande c
JOIN (
    SELECT commande_id, SUM(prix_total) AS total
    FROM commande_ligne
    GROUP BY commande_id
) lc
ON c.id = lc.commande_id
SET c.cache_prix_total = lc.total;
```

7. Obtenir le montant global de toutes les commandes, pour chaque mois

```
SELECT SUM(cache_prix_total), MONTH(date_achat) AS mois
FROM commande
GROUP BY mois;
```

8. Obtenir la liste des 10 clients qui ont effectué le plus grand montant de commandes, et obtenir ce montant total pour chaque client.

```
SELECT client.prenom, client.prenom, SUM(commande.cache_prix_total) AS tc
FROM client
JOIN commande on commande.client_id=client.id
GROUP BY client.id
ORDER BY tc DESC
LIMIT 10;
```

9. Obtenir le montant total des commandes pour chaque date

```
SELECT commande.date_achat, SUM(commande.cache_prix_total)
FROM commande
GROUP BY commande.date_achat;
```

10.  Ajouter une colonne intitulée “category” à la table contenant les commandes. Cette colonne contiendra une valeur numérique

```
ALTER TABLE commande
ADD category INT;
```

11. 1. Enregistrer la valeur de la catégorie, en suivant les règles suivantes :
    - “1” pour les commandes de moins de 200€
    - “2” pour les commandes entre 200€ et 500€
    - “3” pour les commandes entre 500€ et 1.000€
    - “4” pour les commandes supérieures à 1.000€

```
UPDATE commande c
SET c.category = CASE
	WHEN c.cache_prix_total<200 THEN 1
    WHEN c.cache_prix_total>=200 AND c.cache_prix_total<500 THEN 2
    WHEN c.cache_prix_total>=500 AND c.cache_prix_total<1000 THEN 3
    ELSE 4
    END;
```

12. Créer une table intitulée “commande_category” qui contiendra le descriptif de ces catégories

```
CREATE TABLE commande_category(
    id INT PRIMARY KEY,
    type VARCHAR(255)
);
```

13. Insérer les 4 descriptifs de chaque catégorie au sein de la table précédemment créée

```
INSERT INTO commande_category (id, commande_category.type)
VALUES
	(1, "Commandes de moins de 200"),
	(2, "Commandes entre 200 et 500"),
    (3, "Commandes entre 500 et 1000"),
    (4, "Commandes de plus de 1000");
```

14. Supprimer toutes les commandes (et les lignes des commandes) inférieur au 1er février 2019. Cela doit être effectué en 2 requêtes maximum

```
DELETE FROM commande_ligne cl
WHERE cl.commande_id in (SELECT c.id
                         FROM commande c
                         WHERE c.date_achat<='2019-02-01');

DELETE FROM commande
WHERE date_achat<='2019-02-01';
```