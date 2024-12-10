# Révision PHP
## Les variables :
Pour déclarer une variable en PHP, il faut commencer par un symbole dollar ($), suivi du nom de la variable. Le nom de la variable doit respecter certaines règles :
-	Il doit commencer par une lettre (a-z, A-Z) ou un underscore (_).
-	Il peut ensuite contenir des lettres, des chiffres (0-9) et des underscores.
-	PHP est sensible à la casse (c'est-à-dire que $variable, $Variable, et $VARIABLE sont trois variables différentes).
PHP est un langage faiblement typé, ce qui signifie que vous n'avez pas besoin de spécifier le type de données d'une variable lors de sa déclaration. Le type est déterminé dynamiquement en fonction de la valeur que vous assignez à la variable.
 ```PHP
$nom = "Timothy"; //String
$age = 22; //int
$prix = 19.99; //float
$estVrai = true or false; //Boolean
$tableau = [22, 35, 59]; //array
```
**Attention. En PHP il faut utilisé un point-virgule ( ; ) à la fin d’une exécution !!!**
## Les tableaux :
En PHP, un tableau (ou array) est une variable spéciale qui permet de stocker plusieurs valeurs sous un même nom. Les valeurs sont stockées dans des positions spécifiques et peuvent être récupérées ou manipulées à l'aide d’une boucle. Il existe 3 principaux types de tableaux en PHP : les tableaux indexés, les tableaux associatifs et les tableaux imbriquée.
1. Tableau Indexé

Un tableau indexé est un tableau où chaque élément est accessible via un indice numérique. Par défaut, les indices commencent à 0, mais vous pouvez aussi spécifier d'autres indices numériques si nécessaire.
```PHP
$tab = ["pomme", "poire", "abricot"];
    foreach($tab as $nbr){
        echo $nbr." ";
    }
```
2. Tableau Associatif

Un tableau associatif utilise des clés personnalisées au lieu d'indices numériques. Les clés peuvent être des chaînes de caractères, ce qui permet de créer des tableaux plus lisibles et intuitifs.
```PHP
$personne = array(
        "nom" => "Timothy",
        "age" => 22,
        "ville" => "Bruxelles"
    );
```
3. Tableau imbriquée

Un tableau imbriquée est un tableau qui contient d'autres tableaux à l'intérieur. Par exemple, vous pouvez créer un tableau où chaque élément est lui-même un tableau.
```PHP
$utilisateurs = [
        [
            'firstanme' => "Julien",
            'sexe' => "H",
            'note' => [16,35,99,40,72]
        ],
        [
            'firstanme' => "Timothy",
            'sexe' => "H",
            'note' => [17,65,39,52,100]
        ],
        [
            'firstanme' => "Catherine",
            'sexe' => "F",
            'note' => [22,97,01,12,87]
        ],
        [
            'firstanme' => "Mateo",
            'sexe' => "H",
            'note' => [15,13,14,26,39]
        ],
        [
            'firstanme' => "Erica",
            'sexe' => "F",
            'note' => [03,02,66,87,92]
        ],
    ];
```
 
## Les conditions :
Les conditions sont des structures de contrôle qui permettent de prendre des décisions dans le programme en fonction de certaines conditions. Elles permettent d'exécuter des morceaux de code spécifiques si une condition donnée est vraie (true) ou fausse (false).
Les principales structures de condition en PHP sont :
If, else, else if, switch
 ```PHP
$age = 22;                 
    if($age < 18){                  
        echo "Vous étes mineur ;)";
    }else if($age >= 18){         
        echo "Vous étes majeur :)";
    }else{
        echo "Erreur";
    }
```
L'instruction switch est utilisée pour exécuter différentes sections de code en fonction de la valeur d'une expression. Elle permet de simplifier des conditions multiples qui compareraient la même variable à plusieurs valeurs possibles. Au lieu d'utiliser plusieurs if ou elseif, le switch rend le code plus lisible et plus compact.
 ```PHP
switch ($jour) {
    case "Lundi":
        echo "Aujourd'hui, c'est lundi.";
        break;
    case "Mardi":
        echo "Aujourd'hui, c'est mardi.";
        break;
    case "Mercredi":
        echo "Aujourd'hui, c'est mercredi.";
        break;
    default:
        echo "Ce n'est ni lundi, ni mardi, ni mercredi.";
}
```
## Boucle :
Les boucles en PHP permettent de répéter un bloc de code plusieurs fois tant qu'une condition est vraie, ou jusqu'à ce qu'une condition soit atteint. Elles sont essentielles pour éviter la duplication de code et pour effectuer des actions répétitives de manière concise.
1. La boucle while

La boucle while exécute un bloc de code tant qu'une condition est vraie. La condition est vérifiée avant chaque itération.
 ```PHP
    $i = 1;
    while ($i <= 5) {
    echo "i : $i\n";
    $i++;
}
```
2. La boucle for

La boucle for est utilisée quand vous connaissez le nombre d'itérations à l'avance. Elle permet de définir une variable d'initialisation, une condition de continuation, et une expression d'incrémentation en une seule ligne.
 ```PHP
for ($i = 1; $i <= 5; $i++) {
    echo "i : $i\n";
}
```
3. La boucle foreach

La boucle foreach est spécifiquement conçue pour afficher des tableaux ou des objets. Elle permet d'accéder à chaque élément du tableau directement, sans avoir à gérer un indice manuellement.
 ```PHP
$personne = array(
        "nom" => "Timothy",
        "age" => 22,
        "ville" => "Bruxelles"
    );
    foreach($personne as $valeur){
        echo $valeur. " ";
    }
```
## Les fonctions :
Les fonctions en PHP sont des blocs de code réutilisables qui exécutent une tâche spécifique. Elles permettent d'encapsuler une logique pour éviter la répétition de code, facilitant ainsi la maintenance et l'organisation du programme.
Il est conseillée de typée les fonctions pour éviter les erreurs.
 ```PHP
function additionner(int $a, int $b): int {
    return $a + $b;
}
$resultat = additionner(2,2);
echo $resultat;
```
## Les fonctions intégrées :
Les fonctions intégrées en PHP (ou fonctions natives) sont des fonctions qui sont déjà définies dans le langage PHP, et que vous pouvez utiliser sans avoir à les définir vous-même. Ces fonctions couvrent une large gamme de tâches courantes, comme la gestion des chaînes de caractères, des tableaux, des dates, la manipulation de fichiers, des opérations mathématiques, des opérations sur des bases de données, et bien plus encore.

`strlen()` : Retourne la longueur d'une chaîne.

`strtoupper()` : Convertit une chaîne en majuscules.

`str_replace()` : Remplace toutes les occurrences d'une sous-chaîne par une autre.

`substr()` : Extrait une portion d'une chaîne.

`count()` : Retourne le nombre d'éléments dans un tableau.

`array_push()` : Ajoute un ou plusieurs éléments à la fin d'un tableau.

`Rand()` : La fonction rand() en PHP est utilisée pour générer un nombre aléatoire.

`Readline()` : Permet de demander à l’utilisateur d’entrer une valeur.

`Is_numeric()` : Permet de vérifier qu’une valeur est bien numeric (int, float).

## Require et include :
require et include sont des structures utilisées pour inclure et exécuter du code d'un autre fichier PHP dans le fichier en cours d'exécution. Les deux ont un fonctionnement similaire, mais il existe des différences importantes.
1. include

include est utilisé pour inclure et exécuter un fichier PHP dans le fichier principal à l'endroit où la fonction est appelée.
•	Si le fichier inclus est introuvable, PHP affiche un avertissement (warning), mais le script continue son exécution.
•	Utilisé lorsque le fichier à inclure n'est pas critique pour le bon fonctionnement du programme, ou lorsque vous souhaitez que le script continue même si le fichier inclus est manquant.

2. require

require fonctionne de manière similaire à include, mais avec une différence importante : si le fichier n'est pas trouvé, PHP renverra une erreur fatale (fatal error) et arrêtera l'exécution du script. Cela est utile pour les fichiers qui sont essentiels pour le bon fonctionnement de l'application (par exemple, des fichiers de configuration, des classes nécessaires, etc.).
•	Utilisé lorsque l'absence du fichier inclus rend le reste du programme inutilisable ou incorrect.
