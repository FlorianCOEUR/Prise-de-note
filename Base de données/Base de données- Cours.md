

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
