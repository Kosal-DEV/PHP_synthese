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
-	Si le fichier inclus est introuvable, PHP affiche un avertissement (warning), mais le script continue son exécution.
-	Utilisé lorsque le fichier à inclure n'est pas critique pour le bon fonctionnement du programme, ou lorsque vous souhaitez que le script continue même si le fichier inclus est manquant.

2. require

require fonctionne de manière similaire à include, mais avec une différence importante : si le fichier n'est pas trouvé, PHP renverra une erreur fatale (fatal error) et arrêtera l'exécution du script. Cela est utile pour les fichiers qui sont essentiels pour le bon fonctionnement de l'application (par exemple, des fichiers de configuration, des classes nécessaires, etc.).
-	Utilisé lorsque l'absence du fichier inclus rend le reste du programme inutilisable ou incorrect.

## Programmation Orientée Objet en PHP

La Programmation Orientée Objet (POO) en PHP permet d'organiser le code en utilisant des classes et des objets, ce qui favorise la modularité et la réutilisation du code.

**1. Concepts de Base**

Classes et Objets :

Une classe est un modèle définissant les propriétés et méthodes d'un objet.

Un objet est une instance d'une classe.
```PHP
class Voiture {
    public $marque;
    public $couleur;
    
    public function __construct(string $marque, string $couleur) {
        $this->marque = $marque;
        $this->couleur = $couleur;
    }
    
    public function rouler() {
        return "La voiture $this->marque $this->couleur roule.";
    }
}

$maVoiture = new Voiture("Toyota", "rouge");
echo $maVoiture->rouler();
```
Propriétés : Variables définies dans une classe (ex: $marque, $couleur).

Méthodes : Fonctions définies dans une classe (ex: rouler()).

**2. Encapsulation**

L'encapsulation protège l'accès aux propriétés d'une classe grâce aux modificateurs d'accès :

public : accessible partout.

private : accessible uniquement dans la classe.

protected : accessible dans la classe et ses sous-classes.
```php
class Personne {
    private $nom;
    
    public function __construct($nom) {
        $this->nom = $nom;
    }
    
    public function getNom() {
        return $this->nom;
    }
}

$personne = new Personne("Alice");
echo $personne->getNom();
```

## Getter et setter :

Les getters et setters sont des méthodes utilisées pour accéder et modifier des propriétés privées d'une classe.

__Pourquoi les utiliser ?__

En programmation orientée objet, il est recommandé de garder les propriétés d'une classe privées (private) pour éviter qu'elles soient directement modifiées de l'extérieur. On utilise alors :

Les getters pour récupérer la valeur d'une propriété.
Les setters pour modifier la valeur d'une propriété.
```php
class Personne {
    private $nom; // Propriété privée

    // Constructeur
    public function __construct($nom) {
        $this->nom = $nom;
    }

    // Getter pour récupérer la valeur de $nom
    public function getNom() {
        return $this->nom;
    }

    // Setter pour modifier la valeur de $nom
    public function setNom($nouveauNom) {
        $this->nom = $nouveauNom;
    }
}

// Création d'un objet
$personne = new Personne("Alice");

echo $personne->getNom(); // Affiche "Alice"

$personne->setNom("Bob"); // Modification de la propriété via le setter

echo $personne->getNom(); // Affiche "Bob"
```

## L'héritage en POO :

L'héritage permet à une classe (classe enfant) de réutiliser les propriétés et méthodes d'une autre classe (classe parent). Une classe enfant peut également surcharger une méthode de la classe parent.

Classe parent :
```php
class Humain{
    protected string $yeux;
    protected string $nez;
    protected string $bras;

    public function __construct(string $desYeux, string $unNez, string $desBras){
        $this->yeux = $desYeux;
        $this->nez = $unNez;
        $this->bras = $desBras;
    }
    public function respirer(): void{
        echo "Vous respirez !<br>";
    }
    public function mourir(): void{
        echo "Vous êtes mort !!!<br>";
    }
}
```

Class enfant qui hérite de parent :
```php
class Femme extends Humain{
    private string $poitrine;
    public function __construct(string $desYeux, string $unNez, string $desBras, string $unePoitrine){
        parent::__construct($desYeux, $unNez, $desBras);
        $this->poitrine = $unePoitrine;
    }
    public function accoucher(): void{
        echo "Elle accouche !!<br>";
    }
}
```

# PHP Data Objects (PDO)

## Introduction
**PDO (PHP Data Objects)** est une extension de PHP qui fournit une interface uniforme pour interagir avec différentes bases de données. Contrairement à `mysqli`, PDO est orienté objet et supporte plusieurs SGBD.

## Avantages de PDO
- **Portabilité** : Fonctionne avec divers systèmes de gestion de bases de données (MySQL, PostgreSQL, SQLite, etc.).
- **Sécurité** : Protège contre les injections SQL grâce aux requêtes préparées.
- **Flexibilité** : Gère les erreurs de manière élégante avec les exceptions.
- **Performances** : Optimisé pour de meilleures performances avec les requêtes préparées.

## Connexion à une Base de Données
```php
$dsn = "mysql:host=localhost;dbname=ma_base;charset=utf8";
$username = "root";
$password = "";
$options = [
    PDO::ATTR_ERRMODE => PDO::ERRMODE_EXCEPTION, // Gestion des erreurs
    PDO::ATTR_DEFAULT_FETCH_MODE => PDO::FETCH_ASSOC, // Mode de récupération des données
    PDO::ATTR_EMULATE_PREPARES => false // Désactive l'émulation des requêtes préparées (meilleure sécurité)
];

try {
    $pdo = new PDO($dsn, $username, $password, $options);
    echo "Connexion réussie";
} catch (PDOException $e) {
    die("Erreur de connexion : " . $e->getMessage());
}
```

La fonction die() dans le catch sert à arrêter immédiatement l'exécution du script et afficher un message d'erreur.
## Requêtes avec PDO
### Requête Simple
```php
$sql = "SELECT * FROM utilisateurs";
$stmt = $pdo->query($sql);
$utilisateurs = $stmt->fetchAll();
```

La fonction query() en PDO est utilisée pour exécuter directement une requête SQL simple qui ne contient pas de paramètres. Elle est souvent utilisée pour les requêtes de type SELECT.

### Requête Préparée (Sécurisée)
```php
$sql = "SELECT * FROM utilisateurs WHERE email = :email";
$stmt = $pdo->prepare($sql);
$stmt->execute(['email' => 'exemple@email.com']);
$resultat = $stmt->fetch();
```

### Insertion de Données
```php
$sql = "INSERT INTO utilisateurs (nom, email) VALUES (:nom, :email)";
$stmt = $pdo->prepare($sql);
$stmt->execute([
    'nom' => 'John Doe',
    'email' => 'john.doe@email.com'
]);
```

### Mise à Jour de Données
```php
$sql = "UPDATE utilisateurs SET nom = :nom WHERE id = :id";
$stmt = $pdo->prepare($sql);
$stmt->execute([
    'nom' => 'Jane Doe',
    'id' => 1
]);
```

### Suppression de Données
```php
$sql = "DELETE FROM utilisateurs WHERE id = :id";
$stmt = $pdo->prepare($sql);
$stmt->execute(['id' => 1]);
```

## Conclusion
PDO est un outil puissant et sécurisé pour interagir avec les bases de données en PHP. Il facilite la gestion des erreurs, améliore la sécurité et offre une flexibilité accrue grâce à son support multi-SGBD.
