# Les bases:

### 1. La syntaxe

```php
<?php
echo "Hello world!";
?>
```

### 2. Les variables:
```php
$nom = "Florian";
$age = 36;
$taille = 1.85;
$homme = true;
```

### 3. L'affichage:

#### 3.1 La base
```php
<?php
echo $nom;
print_r($tableau);
var_dump($age);
?>
```
#### 3.2 La concaténation:
```php
echo "<h1>Bienvenue ".$name."</h1>";
```


### 4. Structures de contrôle
```php
if ($name == "jean"){
	echo "Utilisateur enregistré";
}else{
	echo "utilisateur inconnu";
}

$jour = "Mardi";
switch ($jour){
	case "Lundi":
		echo "C'est le début de la semaine";
		break;
	case "Mardi":
		echo "Deuxième jour de la semaine";
		break;
	default:
		echo "J'avais la flemme";
}
```

Si on souhaite arrêter le programme, nous pouvons utiliser `exit;`

### 5. Les boucles

```php
for ($i=0; $i>5; $i++){
	echo $i;
}

foreach ($fruits as $fruit){
	echo $fruit; //$fruits est un tableau de fruits
}

$compteur = 1;
while($compteur<=5){
echo "Compteur : $compteur<br>";
$compteur++;
}

$compteur=1;
do{
	echo "Compteur : $compteur<br>";
	$compteur++;
}while($compteur<=5);
```


### 6. Les fonctions

##### 6.1 Définir une fonction:
```php
function saluer($nom){
	return "Bonjour, $nom!";
}

function increaseStock(array $meubles):void{
	foreach($meubles as $meuble){
	$meuble["stock"]++;
	}
}
```