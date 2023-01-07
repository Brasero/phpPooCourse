# POO : L'héritage # 

## Qu'est-ce que l'héritage ? ##

L'héritage est un mécanisme qui permet de créer une nouvelle classe à partir d'une classe existante. C'est-à-dire que l'on peut créer une classe fille à partir d'une classe mère. La classe fille hérite des attributs et des méthodes de la classe mère.

> Exemple : La classe `Etudiant` hérite des attributs et des méthodes de la classe `Personne`.

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

class Etudiant extends Personne {
    public $matricule;
    public $filiere;
}

$etudiant = new Etudiant();
$etudiant->nom = "Doe";
$etudiant->prenom = "John";
$etudiant->age = 20;
$etudiant->adresse = "New York";

echo $etudiant->nom; // Affiche "Doe"
echo $etudiant->prenom; // Affiche "John"
echo $etudiant->age; // Affiche 20
echo $etudiant->adresse; // Affiche "New York"
?>
```

## Comment créer une classe fille ? ##

Pour créer une classe fille, il faut utiliser le mot clé `extends` suivi du nom de la classe mère. Ensuite, on ouvre les accolades `{}` et on écrit les attributs et les méthodes de la classe fille.

> Exemple : Pour créer la classe `Etudiant`, on écrit :

``` php
<?php

class Etudiant extends Personne {
    // Attributs
    public $matricule;
    public $filiere;

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

## Comment utiliser l'héritage ? ##

Pour utiliser l'héritage, il faut créer un objet à partir de la classe fille. Ensuite, on peut utiliser les attributs et les méthodes de la classe fille.

> Exemple : Pour utiliser l'héritage, on écrit :

``` php
<?php

$etudiant = new Etudiant();
$etudiant->nom = "Doe";
$etudiant->prenom = "John";
$etudiant->age = 20;
$etudiant->adresse = "New York";

echo $etudiant->nom; // Affiche "Doe"
    
?>
```

## Comment utiliser les attributs et les méthodes de la classe mère ? ##

Pour utiliser les attributs et les méthodes de la classe mère, il faut utiliser le mot clé `parent` suivi du nom de la méthode ou de l'attribut.

> Exemple : Pour utiliser les attributs et les méthodes de la classe mère, on écrit :

``` php
<?php

class Etudiant extends Personne {
    // Attributs
    public $matricule;
    public $filiere;

    // Méthodes
    public function manger() {
        parent::manger();
    }

    public function dormir() {
        parent::dormir();
    }

    public function travailler() {
        parent::travailler();
    }
}

?>
```

## Comment utiliser les attributs et les méthodes de la classe fille ? ##
Pour utiliser les attributs et les méthodes de la classe fille, il faut utiliser le nom de la méthode ou de l'attribut.

> Exemple : Pour utiliser les attributs et les méthodes de la classe fille, on écrit :

``` php
<?php

class Etudiant extends Personne {
    // Attributs
    public $matricule;
    public $filiere;

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

## Comment utiliser les attributs et les méthodes de la classe mère et de la classe fille ? ##

Pour utiliser les attributs et les méthodes de la classe mère et de la classe fille, il faut utiliser le mot clé `parent` suivi du nom de la méthode ou de l'attribut de la classe mère et le nom de la méthode ou de l'attribut de la classe fille.

> Exemple : Pour utiliser les attributs et les méthodes de la classe mère et de la classe fille, on écrit :

``` php
<?php

class Etudiant extends Personne {
    // Attributs
    public $matricule;
    public $filiere;

    // Méthodes
    public function manger() {
        parent::manger();
        echo "Je mange";
    }

    public function dormir() {
        parent::dormir();
        echo "Je dors";
    }

    public function travailler() {
        parent::travailler();
        echo "Je travaille";
    }
}

?>
```

## Comment utiliser l'héritage avec plusieurs classes ? ##

Pour utiliser l'héritage avec plusieurs classes, il faut créer une classe fille à partir d'une classe mère. Ensuite, on peut créer une classe fille à partir de la classe fille précédente.

> Exemple : Pour utiliser l'héritage avec plusieurs classes, on écrit :

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

class Etudiant extends Personne {
    public $matricule;
    public $filiere;
}

class EtudiantBoursier extends Etudiant {
    public $bourse;
}

?>
```

## Comment utiliser l'héritage avec plusieurs classes et plusieurs niveaux ? ##

Pour utiliser l'héritage avec plusieurs classes et plusieurs niveaux, il faut créer une classe fille à partir d'une classe mère. Ensuite, on peut créer une classe fille à partir de la classe fille précédente. On peut créer autant de classes filles que l'on veut.

> Exemple : Pour utiliser l'héritage avec plusieurs classes et plusieurs niveaux, on écrit :

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

class Etudiant extends Personne {
    public $matricule;
    public $filiere;
}

class EtudiantBoursier extends Etudiant {
    public $bourse;
}

class EtudiantBoursierLoge extends EtudiantBoursier {
    public $chambre;
}

?>
```


# Conclusion #

Dans ce tutoriel, nous avons vu comment utiliser l'héritage en PHP. Nous avons vu comment créer une classe fille à partir d'une classe mère. Nous avons vu comment utiliser les attributs et les méthodes de la classe mère et de la classe fille. Nous avons vu comment utiliser l'héritage avec plusieurs classes et plusieurs niveaux.
> Vous remarquerez qu'il n'y pas de limite à l'héritable. Vous pouvez créer autant de classes filles que vous voulez. Vous pouvez créer autant de niveaux que vous voulez. C'est un avantage de l'héritage.