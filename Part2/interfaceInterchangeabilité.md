# POO : Les interfaces, objet abstrait et l'interchangeabilité #

## Qu'est-ce qu'une interface ? ##

Une interface est une entité qui possède des signatures de méthodes. Les signatures de méthodes sont des fonctions sans corps.

> Exemple : Une interface `Personne` possède des signatures de méthodes comme la fonction `manger()` qui permet de manger, la fonction `dormir()` qui permet de dormir, la fonction `travailler()` qui permet de travailler, etc.

``` php
<?php
interface Personne {
    public function manger();
    public function dormir();
    public function travailler();
}
?>
```

## Comment créer une interface ? ##

Pour créer une interface, il faut utiliser le mot clé `interface` suivi du nom de l'interface. Ensuite, on ouvre les accolades `{}` et on écrit les signatures de méthodes de l'interface.

> Exemple : Pour créer l'interface `PersonneInterface`, on écrit :

``` php

<?php
interface PersonneInterface {
    // Signatures de méthodes
    public function manger();
    public function dormir();
    public function travailler();
}
?>
```


## Qu'est-ce qu'une implémentation d'interface ? ##

Une implémentation est une entité (classe, classe abstraite, ...) qui possède des attributs et des méthodes dont les méthodes définies par l'interface.


## Comment créer une implémentation d'interface ? ##

Pour créer une implémentation d'interface, il faut utiliser le mot clé `implements` suivi du nom de l'interface. Ensuite, on ouvre les accolades `{}` et on écrit les attributs et les méthodes de l'implémentation.

> Exemple : Pour créer la classe `Etudiant` qui implémente l'interface `PersonneInterface`, on écrit :

``` php
<?php
class Etudiant implements PersonneInterface {
    // Attributs
    public $nom;
    public $prenom;
    public $age;
    public $adresse;
    public $matricule;

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

## Plusieurs objets peuvent-ils implémenter une même interface ? ##

Oui, plusieurs objets peuvent implémenter une même interface.

> Exemple : La classe `Etudiant` et la classe `Professeur` peuvent toutes deux implémenter l'interface `PersonneInterface`.

``` php
<?php
class Etudiant implements PersonneInterface {
    // Attributs
    public $nom;
    public $prenom;
    public $age;
    public $adresse;
    public $matricule;

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

class Professeur implements PersonneInterface {
    // Attributs
    public $nom;
    public $prenom;
    public $age;
    public $adresse;
    public $matricule;

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

## Plusieurs interfaces peuvent-elles être implémentées par un même objet ? ##

Oui, plusieurs interfaces peuvent être implémentées par un même objet.

> Exemple : La classe `Etudiant` peut implémenter les interfaces `PersonneInterface` et `EtudiantInterface`.

``` php
<?php
class Etudiant implements PersonneInterface, EtudiantInterface {
    // Attributs
    public $nom;
    public $prenom;
    public $age;
    public $adresse;
    public $matricule;

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

> P.S. : Ici on imagine que l'interface `EtudiantInterface` existe.


## Comment utiliser une implémentation d'interface ? ##

Pour utiliser une implémentation d'interface, il faut créer un objet à partir de l'implémentation.

> Exemple : On peut créer un objet à partir de l'implémentation `Personne` comme `Personne1`.

``` php
<?php
$personne1 = new Etudiant();
?>
```

# L'objet abstrait #

## Qu'est-ce qu'un objet abstrait ? ##

Un objet abstrait est une classe qui possède des attributs et des méthodes, mais qui ne peut pas être instancié, elle peut également contenir des méthodes abstraites (méthodes à implémenter dans les objets enfant).

> Exemple : La classe abstraite `AbstractPersonne` est un objet abstrait qui possède des attributs comme le nom, le prénom, l'âge, l'adresse, etc. et des méthodes comme la fonction `manger()` qui permet de manger, la fonction `dormir()` qui permet de dormir, la fonction `travailler()` qui permet de travailler, etc.
> Elle possède également une méthode abstraite `seDeplacer()` qui permet de se déplacer.

``` php
<?php
abstract class AbstractPersonne {
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
    
    abstract public function seDeplacer();
}
?>
```

## Comment créer un objet abstrait ? ##
Pour créer un objet abstrait, il faut utiliser le mot clé `abstract` suivi du mot clé `class` suivi du nom de la classe. Ensuite, on ouvre les accolades `{}` et on écrit les attributs et les méthodes de l'objet abstrait.

> Exemple : Pour créer la classe abstraite `AbstractPersonne`, on écrit :

``` php
<?php
abstract class AbstractPersonne {
    // Attributs

    // Méthodes
}
?>
```

## Comment créer une classe qui hérite d'un objet abstrait ? ##
Pour créer une classe qui hérite d'un objet abstrait, il faut utiliser le mot clé `extends` suivi du nom de l'objet abstrait. Ensuite, on ouvre les accolades `{}` et on écrit les attributs et les méthodes de la classe qui hérite de l'objet abstrait.

> Exemple : Pour créer la classe `Etudiant` qui hérite de l'objet abstrait `AbstractPersonne`, on écrit :

``` php
<?php
class Etudiant extends AbstractPersonne {
    // Attributs

    // Méthodes
}
?>
```

> Si l'objet abstrait `AbstractPersonne` possède une méthode abstraite, alors la classe qui hérite de l'objet abstrait doit implémenter cette méthode abstraite.

## Comment utiliser un objet abstrait ? ##
Pour utiliser un objet abstrait, il faut créer un objet à partir de l'objet abstrait.


# L'interchangeabilité #

> L'interchangeabilité est la capacité d'un objet à remplacer un autre objet.

> Les interfaces, les objets abstraits, `mais aussi l'heritage en general`, permettent de créer des objets interchangeables. En effet, si deux objets implémentent la même interface `ou qui étende la même classe ou classe abstraite`, alors ils sont interchangeables, car ils ont les mêmes méthodes.

## Qu'est-ce que l'interchangeabilité ? ##

L'interchangeabilité est la capacité d'une classe à être utilisée à la place d'une autre classe.

> Exemple : La classe `Etudiant` peut être utilisée à la place de la classe `Professeur` car elle implémente l'interface `PersonneInterface`.

``` php
<?php
function manger(PersonneInterface $personne) {
    $personne->manger();
}

$personne1 = new Etudiant();
manger($personne1);
$personne2 = new Professeur();
manger($personne2);
?>
```

> Ici, la fonction `manger()` prend en paramètre un objet de type `PersonneInterface`. On peut donc lui passer un objet de type `Etudiant` car `Etudiant` implémente `PersonneInterface`. On peut aussi lui passer un objet de type `Personne` car `Personne` implémente `PersonneInterface`.

# Comment créer une classe interchangeable ? #

Pour créer une classe interchangeable, il faut que la classe implémente une interface ou étende un objet.

> Exemple : La classe `Etudiant` est interchangeable avec la classe `Professeur` car elles implémentent l'interface `PersonneInterface`.

``` php
<?php
class Etudiant implements PersonneInterface {
    // Attributs
    public $nom;
    public $prenom;
    public $age;
    public $adresse;
    public $matricule;

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

class Professeur implements PersonneInterface {
    // Attributs
    public $nom;
    public $prenom;
    public $age;
    public $adresse;
    public $matricule;

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

> Exemple : La classe `Etudiant` est interchangeable avec la classe `Professeur` car elles étendent la classe `Personne`.

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
}

class Etudiant extends Personne {
    // Attributs
    public $matricule;

    // Méthodes
    public function travailler() {
        echo "Je travaille";
    }
}

class Professeur extends Personne {
    // Attributs
    public $matricule;

    // Méthodes
    public function travailler() {
        echo "Je travaille";
    }
}
?>
```