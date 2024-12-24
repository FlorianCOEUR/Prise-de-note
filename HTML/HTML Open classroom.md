#HTML

Voici la structure de base d'un code HTML

```<!DOCTYPE html>
<html lang="fr">
    <head>
        <meta charset="utf-8">
        <title>Le titre de ma page</title>
    </head>
    <body>
    </body>
</html>
```

 La balise orpheline **`<meta charset="utf-8">`** indique l'encodage utilisé dans le fichier  **`.html`** : cela détermine comment les caractères spéciaux s'affichent (accents, idéogrammes chinois et japonais, etc.).

## Les commentaires:
#commentaire
\<!-- Ceci est un commentaire -->
Attention les commentaires restent visible sur le code source de la page
Il existe un raccourci clavier:
	ctrl+k puis ctrl+c


## Les paragraphes:

Le fichier HTML n'est pas sensible aux retour a la ligne de son code, donc il affichera tout à la suite.
Il est possible de faire des Paragraphes avec la balise \<p>.....</p>

On peut également revenir à la ligne avec la balise orpheline \<br>

## Créer des titres:

Pour créer des titres on utilise les balises \<h1></h1> jusque 6.
Il faut toujours structurer sa page en commençant par un titre de niveau 1`<h1>`, puis structurer l'intérieur avec des titres de niveau 2`<h2>`, puis, si besoin de structurer l'intérieur, utiliser des titres de niveau 3, etc. **Il ne devrait pas y avoir de sous-titre sans titre principal**

## Créer des liste avec les balises `<li>` et `<ul>` ou `<ol>`
#liste
#### Étape 1 : balisez les éléments d'une liste avec `<li> </li>`

Pour baliser les éléments qu'on veut mettre dans une liste, on utilise **`<li> </li>`**  (pour "listed item" ou "élément de la liste" en français). Puis on les insère tous à l'intérieur d'une autre balise pour indiquer s'il s'agit d'une liste à puces ou d'une liste numérotée.

#### Étape 2 : insérez la liste dans des balises `<ul> </ul>` ou `<ol> </ol>`

Les balises **`<ul> </ul>`**(pour "unordered list") permettent d'indiquer qu'on démarre une liste non ordonnée, c'est-à-dire, ce que l'on appelle en français **une liste à puces**.

Les balises `<ol> </ol>|`(pour "ordered list") permettent d'indiquer qu'on démarre une liste ordonnée, autrement dit en français **une liste numérotée**.

```
<h1>Les fruits rouges</h1>
<ul>
   <li>Fraises</li>
   <li>Framboises</li>
   <li>Groseilles</li>
</ul>

<h1>Ma journée</h1>
<ol>
   <li>Je me lève.</li>
   <li>Je mange et je bois de l'eau.</li>
   <li>Je retourne me coucher.</li>
</ol>
```

## Mettre du texte important en valeur:

| **Balises**          | **Traduction par le navigateur** |
| -------------------- | -------------------------------- |
| `<mark> </mark>`     | Surligner le texte.              |
| `<em> </em>`         | Mettre le texte en italique.     |
| `<strong> </strong>` | Mettre le texte en gras.         |

## Créez un lien hypertexte avec la balise `<a>` et l'attribut `href`

Pour faire un lien hypertexte :

1. on utilise la balise`<a>`(pour "anchor") pour indiquer qu'on va rediriger vers un autre endroit,
    
2. puis, on ajoute l'attribut **`href`** suivi de`=`pour annoncer l'endroit vers lequel on veut rediriger,
    
3. on indique explicitement entre  **`" "`**  l'endroit vers lequel le lien doit rediriger,
    
4. enfin, on écrit le texte qui doit s'afficher sur l'hyperlien.
    

À partir de là, il y a des subtilités selon l'endroit où l'on veut rediriger l'utilisateur.

### Créez un lien hypertexte avec `<a>` et `href`
#href #lien #link
#### Créer un lien vers un site existant:

Si vous voulez faire un lien vers un autre site existant en ligne, rien de plus simple, il suffit d'utiliser la méthode de copier l'URL du site entre " "à la suite de l'attribut, comme ceci :

```
	<a href="https://openclassrooms.com/fr/">Accédez à OpenClassrooms</a>
```

#### Créer un lien vers une page de notre site:

Si on souhaite aller sur la page deux de notre site qui se trouve dans le même dossier:
	`<a href="page2.html">Page 2</a>`

Par contre si la page se trouve dans un autre dossier, nous chercherons son chemin, par exemple la page 3 se trouve dans `/contenu`:
	`<a href="contenu/page3.html">Page 3</a>`

### Créez une ancre avec les attributs  `id`  et  `href`
#ancre #anchor

#### Cas numéro 1: l'ancre est plus bas sur la même page
```
<h1>Ma grande page</h1>
<p>
Découvrez nos conseils d’aménagement pour :<br>
    <a href="#cuisine">La cuisine</a><br>
    <a href="#jardin">Le jardin</a><br>
    <a href="#salon">Le salon</a><br>
</p>
<h2 id="cuisine">La cuisine</h2>
<p>... (beaucoup de texte) ...</p>
<h2 id="jardin">Le jardin</h2>
<p>... (beaucoup de texte) ...</p>
<h2 id="salon">Le salon</h2>
<p>... (beaucoup de texte) ...</p>
```

#### Cas numéro 2: l'ancre est sur une autre page

```
<h1>Le Mégamix</h1>
<p>
Rendez-vous quelque part sur la page :<br>
    <a href="index.html#cuisine">La cuisine</a><br>
    <a href="index.html#jardin">Le jardin</a><br>
    <a href="index.html#salon">Le salon</a><br>
</p>
```

#### Astuces:

- `target="_blank"`  fait en sorte que le lien hypertexte ouvre un nouvel onglet :
    

```
<p>Bonjour. Souhaitez-vous apprendre sur <a href="https://openclassrooms.com" target="_blank">OpenClassrooms</a> ?</p>
```

- `href="[mailto:NOMDUMAIL@MAIL.COM](mailto:NOMDUMAIL@MAIL.COM)"`  crée un lien hypertexte qui ouvre la boîte mail avec un nouveau message vide.
    
- `href="NOMDEFICHIER.EXTENSION"`  crée un lien hypertexte qui permet de télécharger un fichier que vous avez placé au préalable dans le même dossier que votre page web.


## Insérer des images
#img 
### Avec la balise orpheline`<img>`

Pour fonctionner, la balise `<img>` a besoin de deux attributs:
	`src`: permet de donner la source de l'image (lien web ou image du serveur)
	`alt`: permet de donner une description à une image

### Ajouter une infobulle avec `title`

Afin d'afficher une bulle d'aide sur vos images, vous pouvez utiliser l'attribut  **`title`** ; (à ne pas confondre avec la balise **`title`** qui permet d'indiquer au navigateur le titre d'une page web).
L'attribut **`title`** est facultatif, contrairement à **`alt`**.
Voici ce que cela peut donner :
```
<img src="montagnes.png" title="Alors, envie de vous balader n'est-ce pas ?" alt="Chemin de randonnée au milieu des montagnes">
```

Le visiteur du site, n'aura qu'à survoler la photo avec la souris pour voir l'infobulle "Alors, envie de vous balader n'est-ce pas ?" apparaître par dessus l'image.

### Créer une miniature cliquable

Il faut posséder deux version de l'image, celle d'origine et une miniature.
Il faut :
	1. Placer les deux images dans un dossier appelé *image*
	2. Afficher la version *montagne_mini.jpg* sur une page
	3. et faire un lien vers la version *montagen.jpg*
```
<p>Vous souhaitez voir l'image dans sa taille d'origine ? Cliquez dessus !<br>
    <a href="images/montagne.jpg"><img src="images/montagne_mini.jpg" alt="Chemin de randonnée au milieu des montagnes" title="Cliquez pour agrandir" ></a>
</p>
```
