
https://sql.sh/exercices-sql/villes-de-france


Réponse 1:
```
	SELECT ville_nom, ville_population FROM `villes_france_free` 
	ORDER BY `villes_france_free`.`ville_population_2012` 
	DESC LIMIT 10;
```

Réponse 2:

```
	SELECT ville_nom, ville_surface 
	FROM villes_france_free 
	ORDER BY ville_surface 
	LIMIT 50;
```

