#conventionalcommits #git-cliff

# Description

Les [Conventional Commits](https://www.conventionalcommits.org/en/v1.0.0/) sont un ensemble de règles pour écrire des messages de commit clairs et uniformes. Ils définissent des types spécifiques pour décrire l’intention d’un commit.

[Git-Cliff](https://git-cliff.org/) peut générer des CHANGELOG.md grâce aux [Conventional Commits](https://www.conventionalcommits.org/en/v1.0.0/) écrit via Git.

Les commits s'écrivent de cette manière : 

`<type>[optional scope]: <description>`
`[optional body]`
`[optional footer(s)]`

# Type

- **feat**  
	**Description** : Ajout d'une nouvelle fonctionnalité.  
	**Exemple** : `feat: ajout de la gestion des utilisateurs`  
	Ce type indique une amélioration importante du code et peut être utilisé pour identifier des ajouts qui déclenchent un changement de version **mineur** (dans une approche de versioning sémantique).

- **fix**  
	**Description** : Correction d’un bug.  
	**Exemple** : `fix: correction d'un bug dans l'authentification`  
	Ce type est utilisé pour résoudre des problèmes existants, et peut déclencher une version **patch**.

- **docs**  
	**Description** : Modification de la documentation uniquement.  
	**Exemple** : `docs: mise à jour du README pour ajouter des exemples`  
	Ce type est réservé aux changements dans la documentation (README, guides, commentaires de code, etc.).

- **style**  
	**Description** : Modifications purement liées au style de code, sans impact fonctionnel.  
	**Exemple** : `style: reformater le code selon les règles ESLint`  
	Cela inclut des ajustements comme l’indentation, l’ordre des imports, ou la suppression d’espaces inutiles.

- **refactor**  
	**Description** : Réorganisation ou amélioration du code sans ajout ni correction de fonctionnalité.  
	**Exemple** : `refactor: simplification de la logique du composant Header`  
	Utilisé pour optimiser ou réorganiser le code tout en gardant les mêmes résultats fonctionnels.

- **perf**  
	**Description** : Amélioration des performances du code.  
	**Exemple** : `perf: optimisation de la requête SQL pour réduire le temps de réponse`  
	Ce type est utilisé pour signaler des améliorations qui rendent le code plus rapide ou plus efficace.

- **test**  
	**Description** : Ajout ou modification des tests.  
	**Exemple** : `test: ajout de tests unitaires pour la fonction de validation`  
	Ce type concerne uniquement les modifications dans les fichiers de tests.

- **chore**  
	**Description** : Changements sans impact sur le code applicatif ou utilisateur.  
	**Exemple** : `chore: mise à jour des dépendances npm`  
	Cela peut inclure des mises à jour d’outils, des scripts ou d’autres tâches annexes.

- **build**  
	**Description** : Changements affectant le système de build ou les dépendances.  
	**Exemple** : `build: ajout de Webpack pour le bundling`  
	Ce type est utilisé pour tout ce qui modifie le processus de compilation ou de génération.

- **ci**  
	**Description** : Modifications liées à l’intégration continue (CI).  
	**Exemple** : `ci: mise à jour du workflow GitHub Actions`  
	Utilisé pour configurer ou corriger des scripts ou pipelines d’intégration continue.

- **revert**  
	**Description** : Annulation d’un commit précédent.  
	**Exemple** : `revert: annule le commit 1234abcd`  
	Utilisé pour indiquer explicitement le retour en arrière sur un changement précédent.

- **config**  
	**Description** : Modifications liées à la configuration ou aux fichiers de configuration.  
	**Exemple** : `config: modification du fichier eslint.config`  
	Cela peut concerner des changements dans des fichiers `.env`, `.eslint`, etc.

- **ci-cd** _(optionnel dans certaines configurations)_  
	**Description** : Changements combinés entre CI/CD qui impactent plusieurs configurations.  
	**Exemple** : `ci-cd: mise en place complète de pipeline automatisé`


## Scope (optional)

Le **scope** dans les messages de commit **Conventional Commits** est une manière facultative mais utile de préciser la portée ou le contexte du changement. En gros, il sert à indiquer **quelle partie du projet ou quel module est affecté** par le commit.

### Pourquoi utiliser un scope ?

- **Plus de clarté et de précision** : Le scope aide à comprendre rapidement **où le changement a lieu**, ce qui est particulièrement utile dans les projets complexes avec plusieurs modules ou fonctionnalités. 
  Par exemple :
    - `fix(ui): correction de l'alignement des boutons` indique que la correction concerne l'interface utilisateur.
    - `feat(api): ajout de l'endpoint pour récupérer les utilisateurs` précise que le changement touche l'API.

- **Facilite la navigation et l’historique** : Lorsque tu regardes l'historique des commits, les scopes te permettent d'identifier rapidement les zones concernées par les changements.
    
- **Meilleure collaboration** : Dans une équipe, les scopes permettent à chacun de savoir quel domaine est affecté, ce qui aide à éviter les conflits ou les chevauchements.
    
- **Organisation pour le release log** : Lorsqu’on génère automatiquement des changelogs (avec des outils comme semantic-release), le scope permet de regrouper les changements par fonction ou composant.
  Par exemple :
		`### Features`
		`- **auth**: ajout de la gestion OAuth2`
		`- **cart**: possibilité de sauvegarder un panier`


### Quand et comment définir un scope ?

#### Quand utiliser un scope ?

- Si le projet est **modulaire** ou **organisé par fonctionnalités**, le scope est très utile.
- Si le changement touche tout le projet (ou n’a pas de contexte spécifique), on peut ignorer le scope.


#### Comment définir un scope ?

- **Utiliser les noms de modules/fonctionnalités** :  
    Exemple : `auth`, `ui`, `api`, `db`, `cart`.

- **Utiliser des noms spécifiques** :  
    Parfois, un changement touche un composant spécifique d’un module, comme `button` dans `ui` :
	`fix(ui-button): corrige le style du bouton principal`

- **Être cohérent** : Utiliser des scopes bien définis dans l'équipe ou le projet pour éviter la confusion.


#### Quelques exemples pratiques

- Avec un scope clair :
	  `feat(api): ajout d'un endpoint pour gérer les utilisateurs`
	  `fix(auth): correction d'un bug lors du login`
	  `test(cart): ajout de tests pour la sauvegarde des paniers`

- Sans scope (changement global) :
	  `chore: mise à jour des dépendances npm`
	  `style: reformattage global avec Prettier`

- Scopes dans des sous-modules :
	  `feat(ui-button): ajout d'une animation au clic`
	  `fix(db-migrations): correction d'un script de migration cassé`


### Bonnes pratiques pour le scope

- **Rester court et clair** : Un scope doit être concis, généralement un mot ou deux.
- **Être cohérent avec le projet** : Si le projet utilise des dossiers spécifiques ou des modules clairement nommés, réutiliser ces noms.
- **Pas obligatoire, mais utile** : Si le scope ne clarifie pas le commit, il est préférable de ne pas le forcer.

Le scope est un complément optionnel mais très utile pour préciser le **contexte exact** d’un commit.

# Body (optional)

Le **body** (corps) d’un message de commit dans les **Conventional Commits** sert à fournir des détails supplémentaires sur le changement apporté. Il n'est pas obligatoire, mais il est particulièrement utile pour expliquer pourquoi le changement a été fait ou comment il fonctionne.

## Description détaillée du problème ou de la fonctionnalité

Explique le contexte ou les raisons derrière le commit. Cela peut inclure :

- Pourquoi ce changement est nécessaire 
- Ce qui était incorrect avant le changement 
- Comment ce changement résout le problème


Exemple :
```
fix(api): correction d'une erreur dans le calcul de l'offset 

L'offset dans la pagination était mal calculé en cas d'utilisation de filtres complexes. Cela entraînait un doublon des résultats dans certaines pages.
```

## Détails techniques du changement

Donne des informations sur ce qui a été modifié et pourquoi. Cela peut inclure :

- Les fichiers ou modules spécifiques impactés 
- Les solutions alternatives envisagées (et pourquoi elles ont été écartées) 
- La méthode utilisée pour résoudre le problème


Exemple : 
```
feat(auth): ajout de la gestion OAuth2

Ce commit ajoute la prise en charge du flux OAuth2 pour l'authentification. 
Cela implique :
- Une nouvelle dépendance ajoutée : `oauth2-client`
- La configuration d'une route `/auth/oauth2/callback`
- La mise à jour de la documentation pour refléter ces changements.

```


## Impact potentiel du changement

Explique les conséquences du changement, en particulier si :

- Des comportements existants ont été modifiés ;
- Il y a des risques ou des effets secondaires possibles ;
- Des étapes spécifiques sont nécessaires pour tester ou déployer ce changement.


Exemple :
```
perf(query): amélioration des performances des requêtes de recherche

Le changement remplace une boucle coûteuse par une requête optimisée 
utilisant des index. Cette optimisation améliore le temps de réponse 
des recherches de 200ms à 50ms en moyenne.

Cependant, ce changement nécessite que tous les index soient correctement créés avant le déploiement.

```


## Instructions pour tester ou valider

Fournis des instructions détaillées pour permettre à d'autres développeurs de valider le commit. Cela peut inclure :

- Les étapes pour reproduire le problème initial ;
- Comment tester le correctif ou la nouvelle fonctionnalité.


Exemple :
```
fix(ui): correction de l'alignement des boutons

Pour tester ce changement :
1. Lancez l'application en mode développement (`npm run dev`).
2. Naviguez vers la page des paramètres utilisateurs.
3. Vérifiez que tous les boutons d'action sont correctement alignés sur les écrans de taille XS et MD.

```


## Liens vers les tickets ou issues

Référence à des tickets, des issues, ou des discussions pertinentes pour fournir un contexte supplémentaire.


Exemple : 
```
fix(validation): correction des validations d'email

Ce changement résout l'issue où les adresses email avec des caractères 
accentués n'étaient pas acceptées.

Référence : https://github.com/monrepo/issues/42

```


## Bonne pratique pour le body

- **Rester clair et concis** : Pas besoin d’un roman ! Expliquer juste ce qui est nécessaire pour comprendre.
- **Utiliser des puces ou des listes** : Si le commit implique plusieurs modifications, structurer le texte pour qu’il soit facile à lire.
- **Être précis** : Éviter les explications vagues ou les détails inutiles.
- **Rédiger à l'impératif** : Suivre le même ton que dans le titre (e.g., "Corrige", "Ajoute").


Exemple :
```
feat(cart): ajout de la possibilité de sauvegarder un panier

Cette fonctionnalité permet aux utilisateurs de sauvegarder leur panier
et de le récupérer ultérieurement.

Changements principaux :
- Ajout d'une nouvelle table `saved_carts` dans la base de données.
- Mise à jour des modèles pour inclure la gestion des paniers sauvegardés.
- Ajout d'un bouton "Sauvegarder" dans l'interface utilisateur.

Pour tester :
1. Créez un panier avec plusieurs articles.
2. Cliquez sur "Sauvegarder".
3. Rechargez la page et vérifiez que le panier est correctement récupéré.

```


# Footer (optional)

Le **footer** dans un message de commit **Conventional Commits** est utilisé pour inclure des **informations supplémentaires ou spécifiques**, notamment des références à des tickets, des issues, ou des informations importantes liées au changement. Il apparaît à la fin du message de commit.

## A quoi sert le footer ?

Le footer est principalement utilisé pour **ajouter des métadonnées** ou des **références formelles**.

### Référencer des tickets ou issues

Tu peux lier le commit à des tickets ou issues d’un outil de gestion comme GitHub, GitLab, Jira, etc. Cela facilite le suivi des problèmes et leur résolution.

- Format classique pour GitHub ou GitLab :
	  `Closes #<numéro de l’issue>`
	  Exemple :
		  `Closes #123`

- Pour Jira ou autres outils :
	  `Resolves PROJ-456`
	  Exemple :
		  `Resolves AUTH-789`

### Signaler des BREAKING CHANGES (changement cassant)

Si un changement introduit une **modification cassante** (breaking change) qui peut affecter les utilisateurs ou le fonctionnement, cela doit être mentionné dans le footer avec un mot-clé spécifique : `BREAKING CHANGE`.

Format : 
```
BREAKING CHANGE: <description de la rupture>

```

Exemple :
```
feat(api): ajout de la pagination sur les résultats

BREAKING CHANGE: L'endpoint `/users` retourne désormais un objet paginé
au lieu d'une liste brute. Les clients doivent adapter leurs appels en
conséquence.

```


### Ajouter des co-auteurs ou mentions

Pour signaler que d’autres personnes ont contribué à ce commit (souvent dans le cadre de pair programming ou de contributions externes), tu peux ajouter les co-auteurs avec `Co-authored-by`.

Format :
```
Co-authored-by: Prénom Nom <email@example.com>

```

Exemple :
```
feat(cart): ajout de la gestion des codes promo

Co-authored-by: Alice Dupont <alice@example.com>
Co-authored-by: Bob Martin <bob@example.com>

```

### Inclure des instructions de déploiement ou notes spécifiques

Si le commit nécessite des actions particulières lors du déploiement ou introduit des conditions spécifiques, tu peux les noter dans le footer.

Exemple : 
```
build(deps): mise à jour de React à la version 18

BREAKING CHANGE: La mise à jour de React nécessite une version minimale de Node.js 16.
Veuillez mettre à jour votre environnement avant de déployer.

```


### Récapitulatif des mots-clés de footer

| **Mot-clé**        | **Description**                                                             |
| ------------------ | --------------------------------------------------------------------------- |
| *Closes*           | Indique qu'une issue ou un ticket est fermé grâce à ce commit.              |
| *Resolves*         | Synonyme de "Closes" (utilisé dans d'autres outils comme Jira).             |
| *BREAKING CHANGES* | Signale une rupture majeure dans la compatibilité ou le comportement.       |
| *Co-authored by*   | Mentionne d'autres contributeurs au commit.                                 |
| *See also*         | Ajoute une référence à une autre issue ou discussion liée, mais non fermée. |

### Bonnes pratiques avec le footer

- **Sois précis et concis** : Rédige des notes claires et faciles à comprendre pour les autres développeurs.
- **Utilise les mots-clés appropriés** : Cela permet à des outils automatiques (comme ceux de génération de changelog) d’interpréter correctement les métadonnées.
- **Ne surcharge pas le footer** : Utilise uniquement les informations importantes ou pertinentes pour le commit.


# Exemple complet

```
feat(auth): ajout du support pour OAuth2

Cette fonctionnalité permet aux utilisateurs de se connecter via OAuth2.
Elle inclut :
- Une nouvelle route `/auth/oauth2/callback`
- Une gestion des tokens dans le backend
- La mise à jour de la documentation API

BREAKING CHANGE: Les utilisateurs doivent configurer leur clé OAuth2
dans le fichier .env sous la variable `OAUTH2_CLIENT_ID` et `OAUTH2_CLIENT_SECRET`.

Closes #45
Co-authored-by: Alice Dupont <alice@example.com>

```