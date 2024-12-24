#CSS #HTML 

# Lier le fichier CSS au fichier HTML

Pour lier les fichiers `.css` et `.html`, vous allez rajouter une ligne dans le fichier `.html` pour indiquer au navigateur d'aller chercher la **feuille de style** (_stylesheet_ en anglais) afin d'afficher la page web avec les propriétés de style qu'on lui a appliquées.
Il faut ajouter ce lien avec la balise orpheline `<link>` entre `<head> </head>`
```
<head>
    <meta charset="utf-8">
    <title>Ma page</title>
    <link href="style.css" rel="stylesheet">
</head>
```

# Appliquer une propriété CSS à une balise HTML

###  1. Appliquer une propriété CSS a une balise HTML
```
h1 {
    color: blue;
}
p {
	color: red;
}
```

### 2. Appliquer une propriété CSS à un élément isolé

1. **créer sa classe en de lifichier .css**
```
.ma-class{
	color: #663399;
}
```
- Pour nommer une classe de manière intelligente, utiliser la manière **BEM**:
En BEM, toutes les classes CSS sans exception commencent nécessairement par le nom du bloc. Par exemple pour le menu : `.menu`.

Si on souhaite ajouter dans notre bloc `.menu` un élément item, on va le nommer `.menu__item`. 
On sépare le bloc de l’élément par deux underscores.
```
	<div class="menu">
		<div class="menu__item">Page 1</div>
	</div>
```
Il est donc facile de lire le code et de comprendre que `.menu__item` est un élément de `.menu`.
Pour le modificateur, on sépare le bloc ou l’élément par deux tirets `.bloc__element--modificateur` :
```
	<div class="menu">
	    <div class="menu__item">Page 1</div>
	    <div class="menu__item  menu__item--is-open">Page 2</div>
	    <div class="menu__item">Page 3</div>
	</div>
```

2. **marquer l'élément avec la classe**
```
<p class="ma-class"> Ceci est un paragraphe avec une autre couleur</p>
```
3. **Appliquer plusieurs propriétés à un élément**

	- Déclarer les styles:
```
.ma-classe {
    color: #663399;
}

.grand-texte {
    font-size: 30px;
}
```
- Utiliser les styles dans `<p>`
```
<body>
    <h1>Titre principal</h1>
    <p>Ceci est le contenu de mon premier paragraphe</p>
    <p class="ma-classe grand-texte">Ceci est le contenu de mon deuxième paragraphe</p>
    <h2 class="grand-texte">Voilà mon sous-titre h2</h2>
</body>
```

### 3. Appliquer une Propriété CSS a un élément unique

1. **créer les propriétés de l'*id* via un # dans le fichier .css**
```
#logo{
	/*indiquer les propriétés CSS*/
}
```

2. **Marquer l'élément unique avec *id* dans le fichier .html
```
<img src="images/imagesjolies.jpg" id="logo">
```


# L'apparence du texte

### 1. Changer la taille en CSS avec font-size

1. **La taille absolue**
La taille absolue s'éxprime en pixel
```
font-size: 16px;
```
2. **En taille relative**
La taille relative s'exprime en `em`,
Si on le fait en HTML:
```
<p class="elem1">Élément 1 : 1em</p>
<p class="elem2">Élément 2 : 1.3em</p>
<p class="elem3">Élément 3 : 2em</p>
```
Avec le CSS:
```
.elem1 {
font-size: 1em;
}

.elem2 {
font-size: 1.3em;
}

.elem3 {
font-size: 2em;
}
```

### 2. Changer la police en CSS avec `font-family`
```
balise
{
    font-family: nom-police;
}
```

Pour utiliser des polices de Google Fonts, il faut:
- copier les `<link>` dans le `<head>` du fichier *html*
```
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Roboto&display=swap" rel="stylesheet">
```
- utiser la propriété `font-family`dans le CSS
```
font-family: 'Roboto', sans-serif;
```

### 3.Mettre en italique la propriété `font-style` en CSS
`font-stle` à deux valeurs possible:
- `italic` : le texte sera mis en italique
- `normal` : le texte sera normal (par défaut)
Si on veut mettre le texte entre`<em>` en italique il faut :
```
em{
	font-style: italic;
}
```

### 4. Mettre du text en gras en CSS avec `font-weight`
La propriété `font-weight` à 3 valeurs possibles:
- `bold` : le texte sera en gras
- `normal` : le texte sera écrit normalement
- `thin` : le texte sera plus fin
Mais il est possible de mettre une valeur de 0 à 900 afin d'avoir un texte plus ou moins épais:

### 5. Souligner du texte en CSS avec `text-decoration`

- - `underline`: souligné ;
- `line-through`: barré ;
- `none`: normal (par défaut, sauf dans le cas des liens).

### 6. Aligner du texte en CSS avec `text-align`

- `left` : le texte sera aligné à gauche (c'est le réglage par défaut) ;
- `center` : le texte sera centré ;
- `right` : le texte sera aligné à droite ;

- `justify` : le texte sera "justifié"
Aligner le texte d'une balise inline, comme  `<span>`,  `<a>`,  `<em>` ,  `<strong>` n'est pas possible. Et c'est logique quand on y pense : on ne peut pas modifier l'alignement de quelques mots au milieu d'un paragraphe.

### 7. Changer la couleur du texte avec `color`
```
h1 {
    color: blue;
}
```
- Sous **forme hexadécimale** (6 chiffres précédés d'un #). Exemple :  `color: #FFC8D3;`
- En **notation RGB** (pour Red Green Blue en anglais). Exemple :  `color: rgb(250,25,118);`. Notez qu'on peut ajouter la notion d'opacité (ou de transparence) avec la notation RGBA, où la dernière valeur correspond à l'opacité :  `color: rgba(250,25,118, 0.5);`

### 7. Changer la couleur d'arrière plan

Pour indiquer la couleur de fond de la page web, il vaut mieux l'appliquer à la balise  `<body>`  . Eh oui,  `<body>`  correspond à l'ensemble de la page web. C'est donc en modifiant sa couleur de fond que l'on changera la couleur d'arrière-plan de la page :
```
body {
    background-color: black; /* Le fond de la page sera noir */
    color: white; /* Le texte de la page sera blanc */
}
```
Toutes les balises qui se trouvent à l'intérieur de `<body>` héritent de ses propriétés, afin d'en avoir d'autre pour `<h1>` par exemple, nous devons ajouter des propriétés a `<h1>` :
```
body {
    background-color: black; /* Le fond de la page sera noir */
    color: white; /* Le texte de la page sera blanc */
}

h1 {
    color: purple;
}
```

### 8. Ajouter une image en CSS avec `background-image`

1. **Appliquez une image de fond derrière un élément HTML**

```
body {
    font-family: sans-serif;
    margin: 0; /* Vous ne connaissez pas encore cette propriété mais elle permet de s'assurer que nos éléments prennent bien toute la largeur de la page */
}

.banniere {
    padding: 100px; /* Vous ne connaissez pas encore cette propriété mais elle permet d'ajouter de l'espace dans notre élément*/
    background-image: url('paysage.jpg');
}

h1 {
    color: white;
    text-align: center;
}
```

2. **Modifier le comportement d'une image de fond**
Pour changer le comportement d'une image de fond, il existe plusieurs propriétés CSS :

- La propriété CSS **`background-attachment`** associée à la valeur  `fixed`  permet de rendre l'image de fond fixe lorsqu'on déroule la page web : `background-attachment: fixed;`
    
-  La propriété CSS **`background-size`** associée à la valeur  `cover`  permet de redimensionner l'image afin qu'elle s'adapte à la taille de l'élément qui la contient (elle garde ses proportions, en rognant la largeur ou la hauteur en fonction de la taille de l'élément qui la contient) :  `background-size: cover;`
    
-  La propriété CSS **`background-position`** associée aux valeurs  `top` ,  `bottom` ,  `left` ,  `center`  ou  `right`  permet d'indiquer où doit se trouver l'image de fond, par exemple :  `background-position: top right;`

### 9. Créer des dégradés avec `linear-gradient`
```
background: linear-gradient(90deg, #8360c3, #2ebf91);
```
Ici, on utilise **`linear-gradient`** mais il existe d'autres manières de créer des dégradés. Si vous voulez de l'inspiration en termes de dégradés, rendez-vous sur [UI Gradients](https://uigradients.com/), et si vous voulez construire vos propres dégradés, je vous conseille [CSS Gradient](https://cssgradient.io/).

### 10. Ajouter de la transparence en CSS avec la propriété `opacity`

La propriété CSS `**opacity**`  permet d'indiquer le niveau d'opacité (c'est l'inverse de la transparence).
- Avec une valeur de 1, l'élément sera totalement opaque : c'est le comportement par défaut.
- Avec une valeur de 0, l'élément sera totalement transparent.

Il faut donc choisir une valeur comprise entre 0 et 1. Ainsi, avec une valeur de 0.6 , votre élément sera opaque à 60 %… et on verra donc à travers !

# Créer des bordures et des ombres en CSS
### 1. Créer des bordures

Le CSS offre un large choix de bordures : `border-width`,  `border-color`,  `border-style`…

Pour aller à l'essentiel, je vous propose ici d'utiliser directement la super-propriété **`border`** qui regroupe l'ensemble de ces propriétés. Vous vous souvenez de la super-propriété  `background`  dans le chapitre précédent ? Cela fonctionne sur le même principe : on va pouvoir combiner plusieurs valeurs.

Avec  **`border`**, on peut utiliser jusqu'à trois valeurs pour modifier l'apparence de la bordure :

1. **La largeur** que l'on définit avec une valeur en pixels (comme 2px).
2. **La couleur** que l'on indique avec un nom de couleur, une valeur hexadécimale, ou une valeur RGB.
3. **Le type de bordure** qui peut être `solid` (un trait simple),  `double` (un double trait), `dotted` (un trait en pointillés), `dashed` (un trait en tirets), ou autre. Vous avez un large panel d'options

Si vous voulez mettre des bordures différentes en fonction du côté (haut, bas, gauche ou droite), vous pouvez le faire sans problème. Dans ce cas, vous devrez utiliser ces quatre propriétés :
1. `border-top`  : bordure du haut.
2. `border-bottom`  : bordure du bas.
3. `border-left`  : bordure de gauche.
4. `border-right`  : bordure de droite.

Il existe aussi des équivalents pour paramétrer chaque détail de la bordure si vous le désirez :
- `border-top-width`  pour modifier l'épaisseur de la bordure du haut,
- `border-top-color`  pour la couleur du haut, etc.

On écrit dans le fichier HTML :
```
<p class="element">Élément</p>
```

Puis dans le CSS:
```
.element {
    border-top: 3px #EB5353 dotted;
    border-right: 3px #F9D923 double;
    border-bottom: 3px #36AE7C dashed;
    border-left: 3px #187498 solid;
}
```
Ce qui donne un éléments avec 4 styles de bordures différents.
