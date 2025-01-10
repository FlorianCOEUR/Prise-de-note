

# Qu'est-ce qu'une base de données?
C'est un ensemble de collections faites de table de données.
Une table est un table->tableau de colonne et de ligne
	cela représente une **Entité**/une collection d'objets!
Une table ne représente qu'un seul type de données

| Stagiaire |
| :-------- |
| **Id**    |
| Nom       |
| Prénom    |
**id** : est une clé primaire, il identifie de manière unique un enregistrement.
On utilisera MySQL ou MariaDB qui sont des SGBDR.
SGBDR: Système de gestion de Bases de Données Relationnelles
![[mysql-aide-memoire-sql.pdf]]

![[cours-sql-sh-.pdf]]


## Créer une base de donnée

`CREATE DATABASE devweb_1;`
Ne pas oublier le ;

## Se connecter à une DB

 `use devweb_1`

## Créer une table
```
CREATE TABLE utilisateur ( 
	id INT PRIMARY KEY NOT NULL, 
	nom VARCHAR(100), 
	prenom VARCHAR(100), 
	email VARCHAR(255)
	);
```
Pour Ajouter une auto incrémentation de id: AUTO_INCREMENT
## Supprimer une table
```
DROP TABLE nom_de_la_table
```


# Conception de DB

## 1. Modèle conceptuel de données (MCD)

Cela vient de la Méthode MERISE!


![[BDD-MCD.png]]
## 2.Modèle Logique de Données (MLD)

En MLD, on parle de TABLE comme dans une BDD

![[BDD-MLD-1,N.png]]
N:N -> Many to Many
![[BDD-MLD-N,N.png]]
Dans la Table film_categorie, le couple des deux clés étrangères forment une clé primaire.


### Création de tables:

```
	-- Création de la table 'film' 
	CREATE TABLE film ( 
		film_id INT AUTO_INCREMENT PRIMARY KEY, 
		film_titre VARCHAR(100) NOT NULL ); 
	-- Création de la table 'categorie' 
	CREATE TABLE categorie ( 
		cat_id INT AUTO_INCREMENT PRIMARY KEY, 
		cat_nom VARCHAR(50) NOT NULL ); 
	-- Création de la table de relation 'film_categorie' 
	CREATE TABLE film_categorie ( 
		film_id INT, 
		cat_id INT, 
		PRIMARY KEY (film_id, cat_id), 
		FOREIGN KEY (film_id) REFERENCES film(film_id), FOREIGN KEY (cat_id) REFERENCES categorie(cat_id) );
```

Exercice:
A partir de ce MLD faire des requêtes
![[Exo_BDD_Monde.png]]

1. Nombre d'habitants par pays
```
SELECT nom_pays, SUM(habitant_ville) AS habitants
FROM pays
LEFT JOIN villes ON villes.id_pays=pays.id_pays
GROUP BY nom_pays
ORDER BY habitants;
```

2. Nombre de ville par Pays
```
SELECT nom_pays, COUNT(nom_ville) AS nb_villes
FROM pays
LEFT JOIN villes ON villes.id_pays=pays.id_pays
GROUP BY nom_pays
ORDER BY nb_villes DESC;
```

3. Ville la plus grande
```
SELECT nom_ville, superficie_ville FROM villes
WHERE superficie_ville=(SELECT MAX(superficie_ville) FROM villes);
```

4. 10 villes les plus peuplées
```
SELECT nom_ville, habitant_ville FROM villes
ORDER BY habitant_ville DESC
LIMIT 10;
```

5. La liste des pays avec leur villes
```
SELECT nom_pays, GROUP_CONCAT(nom_ville)
FROM pays
LEFT JOIN villes ON pays.id_pays=villes.id_pays
GROUP BY nom_pays;
```

6. La liste des Pays ayant une superficie supérieure à la moyenne
```
SELECT p1.nom_pays, SUM(v1.superficie_ville) as taille
FROM pays p1
LEFT JOIN villes v1 ON p1.id_pays=v1.id_pays
GROUP BY p1.nom_pays
HAVING taille>(SELECT AVG(v2.superficie_ville)
                   FROM villes v2 )
ORDER BY taille;  
```