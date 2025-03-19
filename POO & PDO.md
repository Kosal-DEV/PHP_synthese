# Utilisation du Langage Orienté Objet avec PDO

PDO (PHP Data Objects) est une interface d'accès aux bases de données en PHP. Elle permet d'utiliser le langage orienté objet pour interagir avec des bases de données de manière sécurisée et performante. Voici comment utiliser PDO avec la programmation orientée objet (POO) en PHP.

## 1. Connexion à la base de données

La première étape consiste à créer une connexion à la base de données via PDO. Cela se fait en créant un objet PDO et en passant les informations de connexion (DSN, nom d'utilisateur, mot de passe) dans le constructeur.

```php
class Database {
    private $host = 'localhost';
    private $db_name = 'ma_base';
    private $username = 'utilisateur';
    private $password = 'motdepasse';
    private $conn;

    public function getConnection() {
        $this->conn = null;
        try {
            $dsn = "mysql:host={$this->host};dbname={$this->db_name}";
            $this->conn = new PDO($dsn, $this->username, $this->password);
            $this->conn->setAttribute(PDO::ATTR_ERRMODE, PDO::ERRMODE_EXCEPTION);
        } catch (PDOException $exception) {
            echo "Erreur de connexion: " . $exception->getMessage();
        }
        return $this->conn;
    }
}
```

## 2. Exécution de requêtes avec PDO

Une fois la connexion établie, vous pouvez exécuter des requêtes SQL avec PDO. Vous pouvez utiliser `prepare` et `execute` pour exécuter des requêtes sécurisées, en particulier pour éviter les injections SQL.

```php
//Requête de selection
class User {
    private $conn;
    private $table_name = 'utilisateurs';

    public function __construct($db) {
        $this->conn = $db;
    }

    public function read() {
        $query = "SELECT * FROM " . $this->table_name;
        $stmt = $this->conn->prepare($query);
        $stmt->execute();
        return $stmt;
    }
}
```

```php
//Requête d'insertion
class User {
    private $conn;
    private $table_name = 'utilisateurs';

    public function __construct($db) {
        $this->conn = $db;
    }

    public function create($nom, $email) {
        $query = "INSERT INTO " . $this->table_name . " (nom, email) VALUES (:nom, :email)";
        $stmt = $this->conn->prepare($query);
        $stmt->bindParam(':nom', $nom);
        $stmt->bindParam(':email', $email);
        if ($stmt->execute()) {
            return true;
        }
        return false;
    }
}
```

## 3. Exemple complet d'utilisation

Voici un exemple complet de gestion de la connexion et des requêtes avec une classe PDO en utilisant l'orientation objet.

```php
class Database {
    private $host = 'localhost';
    private $db_name = 'ma_base';
    private $username = 'utilisateur';
    private $password = 'motdepasse';
    private $conn;

    public function getConnection() {
        $this->conn = null;
        try {
            $dsn = "mysql:host={$this->host};dbname={$this->db_name}";
            $this->conn = new PDO($dsn, $this->username, $this->password);
            $this->conn->setAttribute(PDO::ATTR_ERRMODE, PDO::ERRMODE_EXCEPTION);
        } catch (PDOException $exception) {
            echo "Erreur de connexion: " . $exception->getMessage();
        }
        return $this->conn;
    }
}

class User {
    private $conn;
    private $table_name = 'utilisateurs';

    public function __construct($db) {
        $this->conn = $db;
    }

    public function create($nom, $email) {
        $query = "INSERT INTO " . $this->table_name . " (nom, email) VALUES (:nom, :email)";
        $stmt = $this->conn->prepare($query);
        $stmt->bindParam(':nom', $nom);
        $stmt->bindParam(':email', $email);
        if ($stmt->execute()) {
            return true;
        }
        return false;
    }

    public function read() {
        $query = "SELECT * FROM " . $this->table_name;
        $stmt = $this->conn->prepare($query);
        $stmt->execute();
        return $stmt;
    }
}

// Utilisation
$database = new Database();
$db = $database->getConnection();

$user = new User($db);
$user->create("Jean Dupont", "jean@exemple.com");

$results = $user->read();
foreach ($results as $row) {
    echo $row['nom'] . " - " . $row['email'] . "\n";
}
```
