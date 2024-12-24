#git #linux 
## 1. A quoi sert GIT?

C'est un système de gestion de versions.
Il existe deux types de commandes distinctes:
	commandes de porcelaines
		commandes de tous les jours
	commandes de plomberies
		 cmd rare pour restaurer git
	
---


## 2. Configuration de Git

Après l'installation, configurez votre nom d'utilisateur et votre adresse e-mail :
```
git config --global user.name "Votre Nom"
git config --global user.email "votre.email@example.com"
```
Vérifiez la configuration :
```
git config --list
```
---


## 3. Initialiser un Projet

1. **Créer un nouveau répertoire et y naviguer :**
    ```
    mkdir mon-projet
    cd mon-projet
    ```
2. **Initialiser un dépôt Git :**
    ```
    git init
    ```
3. **Créer un fichier** `**README.md**` **:**
	```
    echo "# Mon Projet" >> README.md
    ```
4. **Ajouter le fichier au suivi Git :**
    ```
    git add README.md
    ```
5. **Faire un premier commit :**
    ```
    git commit -m "Premier commit : Ajout du fichier README.md"
	```
6. **suppression d'un fichier géré par git: **
	```
	git rm "nomdufichier"
	```
7. **Affichage des fichiers avec hachage: **
	```
	git ls-files --stage
	```
8. **Renommer un fichier :**
	```
	git mv "nom ancien" "nouveau nom"
	```
---
	

## 4. Travailler avec GitHub

Lier le dépôt local à GitHub

1. **Ajouter l'URL du dépôt GitHub comme remote :**
    ```
    git remote add origin https://github.com/votre-nom-utilisateur/mon-projet.git
    ```
2. **Pousser le contenu local vers GitHub :** 
	```
	git push -u origin master
	```
	`-u` crée une association entre la branche locale et la branche distante, facilitant les futurs `git push` et `git pull`.


---

## 5. Travailler sur le Projet

**Faire des modifications et des commits**

1. **Modifiez ou créez des fichiers dans votre projet.**
    
2. **Vérifiez l'état du dépôt :**
    ```
    git status
    ```
3. **Ajouter les modifications :**
	```
    git add nom-du-fichier
    ```
    - Pour ajouter tous les fichiers modifiés :
        ```
        git add .
        ```
    
4. **Faire un commit avec un message descriptif :**
```
    git commit -m "Description de la modification"
```
- Il existe des conventions de nommage des commits à voir sur :
	- https://www.conventionalcommits.org/en/v1.0.0/

5. **Envoyer les modifications sur GitHub**

	Pousser les commits vers le dépôt distant :
```
    git push
``` 

---

## 6. Synchroniser les Modifications

**Récupérer les modifications depuis GitHub**

1. **Pour obtenir les dernières modifications faites par d'autres contributeurs :**
    ```
    git pull
    ```
    - Cela fusionne les modifications distantes dans votre branche locale.


**Gérer les conflits**

1. Si un conflit survient, Git vous informera des fichiers en conflit. Ouvrez ces fichiers dans votre éditeur pour résoudre les conflits manuellement.**
    
2. **Après résolution, marquez les conflits comme résolus :**
    ```
    git add fichier-en-conflit
    ```
    
3. **Finalisez la fusion avec un commit :**
    ```
    git commit -m "Résolution des conflits"
    ```

---

## 7. Système de Branche sur Git

Le système de branches est une fonctionnalité clé de Git qui permet de travailler sur différentes versions d'un projet de manière isolée. Voici une explication détaillée du système de branches et comment l'utiliser.
### Qu'est-ce qu'une Branche ?

Une branche est une version distincte de votre code. Par défaut, Git crée une branche principale appelée `master` ou `main`. Les branches permettent de développer des fonctionnalités, corriger des bugs, ou expérimenter des idées sans affecter le code stable de la branche principale.

### Créer et Utiliser des Branches

1. **Créer une branche**
		```
	git branch "nom de la branche"```

2. **Lister toutes les banches**
	```
	git branch
	```
	La branche actuelle est marquée d'un astérisque dans la liste.
3. **Changer de branche**
	```
	git checkout nom-de-la-branche
	```
4. **Créer et basculer sur une nouvelle branche**
	```
	git checkout -b nom-de-la-branche
	```
5. **Supprimer une branche**
	```
	git branch -D nom-de-la-branche
	```
*Ne jamais modifier un même fichier dans des branches différentes!*

6. **Synchro branche local et distance**
	```
	git push --set-upstream origin nom-de-la-branche
	```

7. **Supprimer une branche distante**
```
	git push origin --delete nom-de-la-branche
```

### Fusionner des branches

Il faut se mettre dans la branche dans laquelle on veut fusionner avec git checkout master
la commande de fusion: 
```
	git merge "nom de la branche à fusionner"
```

### Gestion des conflits
	
Si des conflits arrivent un message d'erreur se fait, il faut ainsi résoudre le conflit avec l'éditeur de code.
1. **Ajouter le fichier:**
	```
	git add fichier-en-conflit
	```

2. **Finaliser la fusion avec un commit:**
	```
	git commit -m "Résolution de conflits"
	```

### Naviguer dans les branches
#### Dans les branches locales

1. **Déplacer une branche**
	- `git branch -f a-deplacer cible`

2. **Faire une modification de la branche**
	- `git commit --amend`

3. **Mettre un tag sur un commit**
	- `git tag "nom-du-tag" "cible"`
		- S'il n'y a pas de cible, le tag se fera sur la cible du head
		
4. **Copier une série de commit:**
	- Quand on connait les id des commit :
		`git cherry-picky commit1 commit2 ...`
	- Quand on ne connait pas les id des commit:
		`git rebase -i *branche*`

#### Dans les branches distantes

1. **Cloner une branche:**
	```
	git clone
	```
2. **MAJ des données locales:**

	- `git fetch <remote> <place>`
		- `remote`: table distante généralement *origin*
		- `place` : d'où nous souhaitons mettre à jour, on aussi ecrire *source*:*destination*
	- `git pull <remote> <place>`
		- Ici le fonctionnement est le même que pour `fetch` sauf que `pull` fait un merge après.
		- Nous pouvons aussi utiliser `git pull --rebase` afin de faire un rebase au lieu d'un merge
3. **MAJ des données distantes:**

	- `git push <remote> <place>`
		les arguments sont les mêmes que pour `fetch` ou `pull`
