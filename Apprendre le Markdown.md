
C’est en pratiquant qu’on apprend le mieux. Avant d’aller plus loin dans ce tutoriel, je vous propose d’utiliser [cette page](https://spec.commonmark.org/dingus/) — qui est aussi un valideur syntaxique —, à moins que vous n’ayez déjà installé _Obsidian_. Si tel est le cas, je vous propose de créer une page “Test” et de vous amuser en testant au fur et à mesure de votre lecture.

_Markdown_ existe en [différentes « saveurs »](https://legerement-serieux.ch/diff%C3%A9rentes+saveurs+de+Markdown) (“flavors”, en anglais), c’est-à-dire que, selon que vous l’utilisez dans _Obsidian_, dans _Wordpress_ ou ailleurs, il y a de menues différences, des « extensions » qui sont disponibles ou pas. Mais ne vous faites aucun souci, _Obsidian_ colle de très près à ce qui est le plus standard, y compris dans ce qu’il ajoute au « basique » et qu’on pourrait considérer comme des _extensions_. Il a tout ce qu’il faut pour bien travailler.

### Le texte « normal » 

En _Markdown_, un paragraphe, c’est du texte au kilomètre. C’est « tout le texte jusqu’à la prochaine ligne vide ». Ce sont les lignes vides qui délimitent les paragraphes. On peut en mettre autant qu’on veut, les lignes vides supplémentaires sont ignorées, conformément à la bonne pratique de la typographie. C’est juste pour la lisibilité du texte source qu’on peut en rajouter. Personnellement, j’en ajoute volontiers au-dessus des titres pour repérer plus facilement les blocs logiques.

Quand on souhaite un « retour à la ligne sans commencer un nouveau paragraphe », on termine la ligne par deux espaces, comme ceci (j’ai matérialisé les espaces par des points)  :

> Une première ligne, dont le texte…･･  
> continue sur une deuxième…･･  
> et se termine sur une troisième.

**Une petite particularité** d’_Obsidian_ : quand on écrit des fiches, c’est assez souvent, qu’on veut aller à la ligne sans créer un nouveau paragraphe. Alors, dans _Obsidian_, on peut le faire — “just do it !” Mais, pour que ça fonctionne, il ne faut PAS activer cette préférence, dans le panneau “Editor” des préférences :

![Strict line breaks preference.png](https://publish-01.obsidian.md/access/9d6301c45290f9c02c50f89e8eba97a3/Extras/Assets/Strict%20line%20breaks%20preference.png)

C’est une toute petite entorse au purisme qu’on peut parfaitement se permettre dans nos fiches. Je vous la recommande.

### Italique et gras 

|Dans le texte source|En mode “lecture”|
|---|---|
|Italique : entre *astériques*.|Italique : entre _astérisques_.|
|Gras : entre **deux astériques**.|Gras : entre **deux astérisques**.|
|Gras-italique : entre ***trois astériques***.|Gras-italique : entre **_trois astérisques_**.|

L’élégance d’_Obsidian_ et d’autres éditeurs de _Markdown_, c’est qu’on peut très bien utiliser les raccourcis clavier `⌘I` et `⌘B` pour mettre en italique ou en gras (“Bold”), comme dans tous les traitements de texte.

### Titres et sous-titres 

On note les titres et sous-titres en commençant la ligne par ==1 à 6 dièses== suivis d’une espace. Le nombre de dièses indique le niveau hiérarchique.

|Dans le texte source|En mode “lecture”|
|---|---|
|# Titre de niveau 1|# Titre de niveau 1|
|## Titre de niveau 2|## Titre de niveau 2|
|### Titre de niveau 3|### Titre de niveau 3|

### Listes 

Il suffit de commencer la ligne par ==un astérisque suivi d’une espace==— pour les listes à puce — ou par ==un nombre suivi d’un point et d’une espace== — pour les listes numérotées. On peut aussi utiliser des `+` ou des `-` (tiret), à la place des astérisques, c’est une question de goût ou d’habitude. À l’arrivée, c’est la feuille de style qui définira l’aspect visuel des choses.

|Dans le texte source|En mode “lecture”|
|---|---|
|Liste à puces :  <br>  <br>* premier item de la liste ; j’en fais un long paragraphe pour démontrer la gestion des retraits ;  <br>* deuxième item de la liste ;  <br>* troisième item de la liste.|Liste à puces :<br><br>- premier item de la liste ; j’en fais un long paragraphe pour démontrer la gestion des retraits ;<br>- deuxième item de la liste ;<br>- troisième item de la liste.|
|Liste numérotée :  <br>  <br>1. premier item de la liste ;  <br>2. deuxième item de la liste ; si le paragraphe se prolonge, *Markdown* fait très bien les choses !  <br>3. troisième item de la liste.|Liste numérotée :<br><br>1. premier item de la liste ;<br>2. deuxième item de la liste ; si le paragraphe se prolonge, _Markdown_ fait très bien les choses !<br>3. troisième item de la liste.|

Comme on peut le voir dans mon document de démonstration, on peut sans autres entremêler un niveau de liste à puce à l’intérieur d’une liste numérotée — ou le contraire.

### Liens 

Pour écrire des liens, on met ==entre crochets== le texte en clair, suivi immédiatement du lien lui-même, ==entre parenthèses==. Comme ceci :

| Dans le texte source                                              | En mode “lecture”                                                  |
| ----------------------------------------------------------------- | ------------------------------------------------------------------ |
| Voici [le site](https://obsidian.md) de l’application *Obsidian*. | Voici [le site](https://obsidian.md/) de l’application _Obsidian_. |

On peut aussi utiliser une syntaxe avec des références, laquelle convient mieux aux liens qui sont longs. Mais j’en déconseille l’utilisation dans _Obsidian_, car elle rend très compliqués le copier-coller et le déplacement des liens d’une fiche à une autre.

### Images 

Pour les images, la syntaxe est exactement la même que celle pour les liens, il suffit d’ajouter un ==point d’exclamation== juste avant le crochet ouvrant.

| Dans le texte source                                                                                                                                                                                                                                                                                | En mode “lecture”                                                                                                                                                          |
| --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Voici le logo de *Wikipedia* :  <br>![La description (optionnelle)]([https://upload.wikimedia.org/wikipedia/commons/thumb/d/de/Wikipedia_Logo_1.0.png/220px-Wikipedia_Logo_1.0.png](https://upload.wikimedia.org/wikipedia/commons/thumb/d/de/Wikipedia_Logo_1.0.png/220px-Wikipedia_Logo_1.0.png)) | Voici le logo de _Wikipedia_ :  <br>![Le logo de Wikipedia](https://upload.wikimedia.org/wikipedia/commons/thumb/d/de/Wikipedia_Logo_1.0.png/220px-Wikipedia_Logo_1.0.png) |
| Voici mon logo :  ![logo Dr O. Spinnler](https://dr-spinnler.ch/myfiles/logos/Logo-Dr.png)                                                                                                                                                                                                          | Voici mon logo : ![logo Dr O. Spinnler](https://dr-spinnler.ch/myfiles/logos/Logo-Dr.png)                                                                                  |

### Notes de bas de page 

C’est une des seules « particularités » d’_Obsidian_ où il s’écarte de ce qui est considéré « standard » : la syntaxe «==un circonflexe== suivi de ==crochets encadrant== le texte de la note », comme ceci :

| Dans le texte source           | En mode “lecture” |
| ------------------------------ | ----------------- |
| Du texte ^[A quick footnote.]. | Du texte.         |

> De toute façon, les notes de bas de page avaient été oubliées par John Gruber quand il a proposé le _Markdown_. Il a donc bien fallu trouver quelque chose, car c’est vraiment souvent qu’on les utilise. Alors, dans _Obsidian_, je vous recommande sans réserve la syntaxe que je viens d’indiquer. Mais sachez qu’ailleurs, c’est plutôt la suivante qui est considérée « standard ». Elle fonctionne aussi dans _Obsidian_, bien évidemment.

Pour les notes plus longues — plus d’un paragraphe —, on procède ainsi : l’appel de note se met entre crochets, le premier caractère étant un circonflexe. L’appel de note peut être un chiffre ou un label descriptif.

Plus loin dans le texte — n’importe où, vraiment —, on reprend le label entre crochets, suivis d’un “deux-points” et l’on écrit le texte de la note. C’est plus difficile à expliquer qu’à montrer ou qu’à utiliser :

| Dans le texte source                                                                        | En mode “lecture” |
| ------------------------------------------------------------------------------------------- | ----------------- |
| Voici une note [^note_démo].  <br>  <br>[^note_démo]: Le texte de la note de démonstration. | Voici une note.   |

Je trouve souvent commode d’utiliser un texte descriptif pour les notes, en particulier quand il y en a plusieurs dans le texte. Ça simplifie grandement l’édition quand on remanie son texte. Mais en mode “lecture”, les notes sont simplement numérotées dans l’ordre chronologique.

### Citations 

Comme dans nos e-mails, il est assez souvent utile de faire des citations. La syntaxe est d’ailleurs la même : il s’agit de commencer les lignes — ou les paragraphes — par des `>`.

|Dans le texte source|Comment c’est rendu par l’interpréteur|
|---|---|
|> Le texte cité.  <br>>  <br>> Un deuxième paragraphe.  <br>>  <br>>> On peut aussi indenter à un deuxième niveau.  <br>>>  <br>>> ### Et même mettre des titres dans les citations  <br>>> Étonnant, non ?  <br>>  <br>>Ici, on revient au niveau 1 de la citation.|> Le texte cité.<br>> <br>> Un deuxième paragraphe.<br>> <br>> > On peut aussi indenter à un deuxième niveau.<br>> > <br>> > ### Et même mettre des titres dans les citations<br>> > <br>> > Étonnant, non ?<br>> <br>> Ici, on revient au niveau 1 de la citation|

### Ligne horizontale 

Dernier élément que j’utilise très régulièrement, la ligne horizontale. Elle peut être utile pour séparer visuellement des idées ou des sections de texte. Je l’utilise généreusement dans mes notes. On l’obtient en tapant ==au moins trois tirets==, seuls dans un paragraphe (= une seule ligne). Pour l’agrément visuel, j’en mets souvent plus (j’ai un raccourci clavier _ad hoc_) :

```
----------------------------------------------
```

↑ cette ligne de tirets sera généralement rendue par une ligne horizontale faisant toute la largeur de la colonne de texte. Dans certaines situations et suivant la feuille de style utilisée, elle pourrait aussi bien être rendue par un ornement ou par un saut de page. Cela pourrait être le cas dans un “e-book”, par exemple.

### Les tables 

La syntaxe n’est pas très compliquée, mais vous n’avez même pas besoin de l’apprendre ! Il suffit, en effet, d’installer le plugin “Advanced Tables” que vous trouverez dans les “Community Plugins”. Faites-le sans hésiter. Une fois que vous l’avez installé, procédez de la manière suivante pour insérer et éditer une table dans votre texte.

1. Laisser une ligne vide puis tapez un “pipe” `|` (`Option–7` sur Mac) suivi d’un `↩︎` (Enter) et vous obtenez ceci :
    
    ![Elementary table — edit mode.png](https://publish-01.obsidian.md/access/9d6301c45290f9c02c50f89e8eba97a3/Extras/Assets/Elementary%20table%20%E2%80%94%20edit%20mode.png)
    
    C’est la plus élémentaire des tables : une cellule d’en-tête, une cellule du corps de la table.
    
2. À partir de là, il est très facile d’éditer la table, grâce au plugin “Advanced Tables”. Si vous avez très peu de texte à mettre dans les cellules, cela suffira.
    
3. Si vous avez beaucoup de texte à mettre dans les cellules, je vous recommande de ne pas insister dans _Obsidian_ et d’éditer la fiche avec _Typora_, qui est le meilleur des éditeurs que je connaisse pour ce faire. ⭢ [Éditer une fiche avec un éditeur externe](https://legerement-serieux.ch/Fiches/PKM/%C3%89diter+une+fiche+avec+un+%C3%A9diteur+externe)
    

### Encore trois choses utiles 

Tout ce que je viens de montrer est disponible partout où l’on trouve du _Markdown_. C’est ce qu’on va utiliser 99 % du temps et ça suffit à la prise de notes et à la confection de nos fiches. J’utilise encore volontiers, parmi les autres possibilités :

- La syntaxe particulière pour les “==todo lists==”  :
    
    `- [ ] item cliquable` qui donne
    
    - [ ] item cliquable
- La possibilité de ==citer du code==, comme quand j’écris que l’extension d’un fichier _Markdown_ est `.md`. Il suffit de mettre entre deux accents graves (“backticks” en anglais) : `.md`.
    
- La possibilité de mettre — quand même — du ==code HTML== au milieu du texte en _Markdown_. C’est ainsi que je mets ma signature (cliquable !) et la date, centrées, au bas des pages de ce site. J’ai évidemment une macro _Typinator_ pour cela !
    
- La possiblité de mettre en évidence du texte avec des `==` comme ceci :
    
    Ceci est du ==texte surligné==, comme avec un [STABILO BOSS](https://www.stabilo.com/fr/produits/surligner/surligneurs/stabilo-boss-original/).
    

Parmi les possibilités que je n’exploite pas — pas encore ? —, je citerai :

- Les références bibliographiques.
- La possibilité d’insérer des équations mathématiques, avec la même syntaxe que pour le _LaTex_ — c’est quelque chose que les scientifiques apprécient.
- Les diagrammes en syntaxe [_Mermaid_](https://mermaid-js.github.io/mermaid/) :