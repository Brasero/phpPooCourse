# POO : Introduction #

## Qu'est-ce que la programmation orientée objet ? ##

La programmation orientée objet est un paradigme de programmation qui permet de structurer un programme en utilisant des objets. Un objet est une entité qui possède des attributs et des méthodes. Les attributs sont des variables et les méthodes sont des fonctions.

## Qu'est-ce qu'une classe ? ##
Une classe est une entité qui possède des attributs et des méthodes. Les attributs sont des variables et les méthodes sont des fonctions.

> Exemple : Une classe `Personne` possède des attributs comme le nom, le prénom, l'âge, l'adresse, etc. et des méthodes comme la fonction `manger()` qui permet de manger, la fonction `dormir()` qui permet de dormir, la fonction `travailler()` qui permet de travailler, etc.

``` php
<?php
class Personne {
    public $nom;
    public $prenom;
    public $age;
    public $adresse;

    public function manger() {
        echo "Je mange";
    }

    public function dormir() {
        echo "Je dors";
    }

    public function travailler() {
        echo "Je travaille";
    }
}
?>
```

## Qu'est-ce qu'un objet ? ##

Un objet est une instance d'une classe. C'est-à-dire que l'on peut créer plusieurs objets à partir d'une même classe.

> Exemple : On peut créer plusieurs objets à partir de la classe `Personne` comme `Personne1`, `Personne2`, `Personne3`, etc.

``` php
<?php
// On déclare la classe Personne avant de l'instancier

$personne1 = new Personne();
$personne2 = new Personne();
$personne3 = new Personne();
?>
```

## Comment créer une classe ? ##

Pour créer une classe, il faut utiliser le mot clé `class` suivi du nom de la classe. Ensuite, on ouvre les accolades `{}` et on écrit les attributs et les méthodes de la classe.

> Exemple : Pour créer la classe `Personne`, on écrit :

``` php
<?php
class Personne {
    // Attributs
    public $nom;
    public $prenom;
    public $age;
    public $adresse;

    // Méthodes
    public function manger() {
        echo "Je mange";
    }

    public function dormir() {
        echo "Je dors";
    }

    public function travailler() {
        echo "Je travaille";
    }
}
?>
```

## Qu'est-ce qu'une instance ? ##

Une instance est une copie d'une classe. C'est-à-dire que l'on peut créer plusieurs instances à partir d'une même classe.

> Le mot clé `new` permet de créer une instance.

> Le résultat de l'instance avec le mot clé `new` est un objet qu'il faut stocker dans une variable.


## Accéder aux attributs et aux méthodes d'un objet ##

Pour accéder aux attributs et aux méthodes d'un objet, on utilise l'opérateur `->`.

> Exemple : Pour accéder aux attributs et aux méthodes de l'objet `$personne1`, on écrit :

``` php
<?php
// On déclare la classe Personne avant de l'instancier

$personne1 = new Personne();

// Accès aux attributs
$personne1->nom = "Dupont";
$personne1->prenom = "Jean";
$personne1->age = 25;
$personne1->adresse = "1 rue de la paix";

// Accès aux méthodes
$personne1->manger();
$personne1->dormir();
$personne1->travailler();
?>
```

## Le constructeur ##

Le constructeur est une méthode qui est appelée automatiquement lors de l'instanciation d'un objet. C'est-à-dire que l'on peut définir des valeurs par défaut pour les attributs de l'objet.

> Exemple : Pour définir des valeurs par défaut pour les attributs de l'objet `$personne1`, on écrit :

``` php
<?php
class Personne {
    // Attributs
    public $nom;
    public $prenom;
    public $age;
    public $adresse;

    // Méthodes
    public function manger() {
        echo "Je mange";
    }

    public function dormir() {
        echo "Je dors";
    }

    public function travailler() {
        echo "Je travaille";
    }

    // Constructeur
    public function __construct($nom, $prenom, $age, $adresse) {
        $this->nom = $nom;
        $this->prenom = $prenom;
        $this->age = $age;
        $this->adresse = $adresse;
    }
}

$personne1 = new Personne("Dupont", "Jean", 25, "1 rue de la paix");
?>
```

## Les autres méthodes magiques ##

Il existe d'autres méthodes magiques comme `__destruct()` qui est appelée automatiquement lors de la destruction d'un objet, `__get()` qui est appelée automatiquement lors de l'accès à un attribut, `__set()` qui est appelée automatiquement lors de la modification d'un attribut, `__isset()` qui est appelée automatiquement lors de la vérification d'un attribut, `__unset()` qui est appelée automatiquement lors de la suppression d'un attribut, etc.

## Les constantes ##

Les constantes sont des variables qui ne peuvent pas être modifiées. Pour déclarer une constante, on utilise le mot clé `const` suivi du nom de la constante et de sa valeur.

> Exemple : Pour déclarer la constante `PI`, on écrit :

``` php
<?php
class Math {
    const PI = 3.14;
}
?>
```

> Pour accéder à une constante, on utilise le nom de la classe suivi du nom de la constante.

> Exemple : Pour accéder à la constante `PI`, on écrit :

``` php
<?php
echo Math::PI;
?>
```

## Les attributs et les méthodes statiques ##
Les attributs et les méthodes statiques sont des attributs et des méthodes qui peuvent être appelés sans avoir besoin d'instancier un objet.

> Exemple : Pour déclarer un attribut ou une méthode statique, on utilise le mot clé `static` devant l'attribut ou la méthode.

``` php
<?php
class Math {
    public static $PI = 3.14;

    public static function addition($a, $b) {
        return $a + $b;
    }
}
?>
```

> Pour accéder à un attribut ou à une méthode statique, on utilise le nom de la classe suivi du nom de l'attribut ou de la méthode.
> Exemple : Pour accéder à l'attribut `PI` et à la méthode `addition()`, on écrit :

``` php
<?php
echo Math::$PI;
echo Math::addition(1, 2);
?>
```