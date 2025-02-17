
# À quoi ça sert?

JS sert à rendre le site interactif pour l'utilisateur

# Comment ajouter un script JS

Dans le code HTML:
```html
<script src "blabla.js"></script>
```

Dans ce cas la, le script est chargé dans la page HTML au moment ou la balise est lue.
Il est possible d'ajouter des attributs à la balise script:
- `async` : Pour charger et lancer le script en même temps que le code HTML
- `defer` :  Pour charger le code au moment que la balise est lue mais lancer à la fin du code une fois que le DOM est construit

Il est donc recommandé pour éviter les erreurs d'utiliser `defer` 

# Comment écrire du JS

Important:
- `;` à la fin de la ligne, il n'est pas obligatoire car js le met automatiquement à votre place, mais il vaut mieux le mettre
Pour déclarer une variable, il n'y a pas besoin de $ comme en php mais il faut déclarer une variable avec:
- `let` : la portée de la variable déclarée est locale
- `var` : la portée de la variable déclarée est globale

JS permet de communiquer avec la console du navigateur avec :
```js
consol.log("Hello");
```

Il est conseillé lorsque nous faisons du JS de garder la console du navigateur ouverte.

# Ecouter des évènements

```js
document.getElementById("id"); //Cibler un élement avec l'id
document.getElementsByTagName("button"); //Cibler les éléments avec la balise button sous forme de tableau d'éléments
document.getElementsByClassName("nomDeclasse"); // Elements avec la classe
document.querySelectorAll("qqch"); //Cibler des élements avec des selecteurs CSS
document.querySelector("qch"); // cibler le premier élement de selecteur CSS
```

Dans notre exemple:
```html
<button id="btn">test</button>
```

```js
let button= document.getElementById("btn");
button.addEventListener("click", function(){

});
```

addEventListener a 2 parametres:
- l'évènement à écouter, ici le clique
- et la fonction qui sera effectuée lors de l'évènement

#### Changer le contenu d'un titre avec du css:
```js
let button= document.getElementById("btn");

button.addEventListener("click", function(){

    let h1=document.querySelector("h1");

    if(h1.innerText == "Hello, World!"){

        h1.innerText="Goodbye!";

        h1.classList.add("erreur");

    }else{

        h1.innerText="Hello, World!";

        h1.classList.remove("erreur");

    }

});
```
```css
.erreur{

    color:#FF0000;

    font-weight:normal;

}
```