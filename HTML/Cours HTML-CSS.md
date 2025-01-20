# Cours 10/01/2025

## 1. Qu'est ce que c'est HTML?

HTML pour HyperText Markup Language
c'est la structure de la page. En gros de définir ce qu'est un titre, du contenu etc.
Il va avoir un impact sur le référencement et également sur l'accessibilité.

## 2. C'est quoi CSS

CSS pour Cascading Style Sheets
Il sert à rendre joli le code HTML

## 3.Premier pas en HTML

Sur VSCode, en appuyant sur `!` et `Entrée` il va afficher la structure de base d'un fichier html
La balise `<titre>` est ce qui va servir au référencement,  au titre de l'onglet, dans les favoris etc.
	Mettre: `nom de la page | nom du site`

Dans le `<body>` il ne peut y avoir qu'une seule balise `<h1>`, elle sera utile pour le référence, c'est le titre affiché de la page!

# Breakpoint 
#breakpoint

les différentes tailles d'écrans:

| <500 px | 768 | 992 | 1200 | 1400 | >1400 |
| ------- | --- | --- | ---- | ---- | ----- |

# NavBar
#navbar
La barre de navigation est une liste de liens.

# Bonne pratique de dev:
Afin de visualiser quel taille d'écran nous avons, il est conseillé de se faire un système mémotechnique afin de visualiser facilement, par exemple mettre une bordure au top du body qui change de couleur suivant la taille de l'écran (largeur)

# Faire une nav bar
#navbar 

Nous avons :
<nav>
	<ul>

		<li><a href=""></a></li>

		<li><a href=""></a></li>

		<li><a href=""></a></li>

		<li><a href=""></a></li>

	</ul>
 </nav>
 Il faut supprimer la puce, la marge a gauche et dire qu'il faut être en ligne
 dans le ul:
 - `list-style-type:none` pour supprimer la puce
 - `padding-left: 0` enlever la marge a gauche
sur les li:
- `display:inline-block` afin de les mettre en ligne
```

```



# Comprendre `Grid`
#grid
Il y a une video à voir :
https://www.youtube.com/watch?v=tcrAaPIZbLo&t=137s&ab_channel=ParfaitementWeb
- `display: grid` Pour définir un grid
- `grid-gap: 10px`: Mettre un espacement de 10px entre chaque élément
- `grid-template-columns: repeat(3, minmax(200px, 1fr)` il y aura donc 3 colonne de au moins `200px`
- `grid-template-row: repeat(2, 300px)`:  il y aura donc 2 rangées de 300px de large.
- `grid-auto-flow: column`: changement du rangement de grid en colonne
- `grid-auto-rows: minmax(50px, auto)`: Pour gérer de manière automatique la hauteur des colonnes
SI on souhaite changer la taille de certains éléments:
```
.card:nth-child(x){
	grid-column: 1/span2;
	grid-row: span 2;
}
```
Ici, l'enfant xieme enfant de la classe card, débutera a la colonne 1 et s'étirera sur 2 colonnes et fera 2 lignes de largeurs