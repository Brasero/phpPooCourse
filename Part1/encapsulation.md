# L'encapsulation ou visibilité #

L'encapsulation est la capacité d'une classe à cacher ses attributs et ses méthodes. Cela permet de protéger les attributs et les méthodes de la classe.

## A quoi sert l'encapsulation ? ##

L'encapsulation permet de protéger les attributs et les méthodes de la classe. Cela permet de ne pas modifier les attributs et les méthodes de la classe.

> Il est utile d'utiliser l'encapsulation pour protéger les attributs et les méthodes de la classe.
>  - Pout indiquer que la méthode ou l'attribut ne doit pas être utilisé ou manipulé par le développeur.
>  - Pour protéger les attributs et les méthodes de la classe et ainsi éviter de les modifier.
>  - En régle générale, il est de bon ton d'utiliser l'encapsulation pour protéger les attributs et les méthodes de la classe.


## Comment utiliser l'encapsulation ? ##

Pour utiliser l'encapsulation, il faut utiliser les mots clés `public`, `private` et `protected`.   
- `public` : permet de rendre l'attribut ou la méthode accessible à l'extérieur de la classe.
- `private` : permet de rendre l'attribut ou la méthode inaccessible à l'extérieur de la classe.
- `protected` : permet de rendre l'attribut ou la méthode accessible à l'intérieur de la classe et à l'intérieur des classes filles.

> Exemple : Pour rendre l'attribut `$nom` de la classe `Personne` accessible à l'extérieur de la classe, on écrit :
> 
> ``` php
> <?php
>   
> class Personne {
>    // Attributs
>   public $nom;
> }
>   
> $personne = new Personne();
> $personne->nom = "Diallo"; // On peut accéder à l'attribut $nom de la classe Personne
> echo $personne->nom; // Affiche Diallo
> ?>
> ```

> Exemple : Pour rendre l'attribut `$nom` de la classe `Personne` inaccessible à l'extérieur de la classe, on écrit :
>   
> ``` php
> <?php
> 
> class Personne {
>   // Attributs
> 
>  private $nom;
> }
> 
> $personne = new Personne();
> $personne->nom = "Diallo"; // Erreur : Fatal error: Uncaught Error: Cannot access private property Personne::$nom
> echo $personne->nom; // Erreur : Fatal error: Uncaught Error: Cannot access private property Personne::$nom> 
> ?>
> ```

> Exemple : Pour rendre l'attribut `$nom` de la classe `Personne` accessible à l'intérieur de la classe et à l'intérieur des classes filles, on écrit :
> 
> ``` php
> <?php
> 
> class Personne {
>  // Attributs
>   protected $nom;
> }
> 
> $personne = new Personne();
> $personne->nom = "Diallo"; // Erreur : Fatal error: Uncaught Error: Cannot access protected property Personne::$nom
> echo $personne->nom; // Erreur : Fatal error: Uncaught Error: Cannot access protected property Personne::$nom
> ?>
> ```
    
## Comment utiliser l'encapsulation avec les méthodes ? ##

Pour utiliser l'encapsulation avec les méthodes, il faut utiliser les mots clés `public`, `private` et `protected`.

> Exemple : Pour rendre la méthode `manger()` de la classe `Personne` accessible à l'extérieur de la classe, on écrit :
> 
> ``` php
> <?php
> 
> class Personne {
>   // Attributs
>   public $nom;
> 
>   // Méthodes
>   public function manger() {
>       echo "Je mange";
>   }
> }
> 
> $personne = new Personne();
> $personne->manger(); // Affiche Je mange> 
> ?>
> ```

> Exemple : Pour rendre la méthode `manger()` de la classe `Personne` inaccessible à l'extérieur de la classe, on écrit :
> 
> ``` php
> <?php
>   
> class Personne {
>   // Attributs
>   public $nom;
> 
>   // Méthodes
>   private function manger() {
>   echo "Je mange";
>   }
> }
>   
> $personne = new Personne();
> $personne->manger(); // Erreur : Fatal error: Uncaught Error: Call to private method Personne::manger() from context
> ?>
> ```

> Exemple : Pour rendre la méthode `manger()` de la classe `Personne` accessible à l'intérieur de la classe et à l'intérieur des classes filles, on écrit :
> 
> ``` php
> <?php
>
> class Personne {
>   // Attributs
>   public $nom;
>   
>   // Méthodes
>   protected function manger() {
>    echo "Je mange";
>   }
> }
> 
> $personne = new Personne();
> $personne->manger(); // Erreur : Fatal error: Uncaught Error: Call to protected method Personne::manger() from context
> ?>
> ```

# Conclusion #

L'encapsulation permet de protéger les attributs et les méthodes de la classe. Cela permet de ne pas modifier les attributs et les méthodes de la classe.
- `public` : permet de rendre l'attribut ou la méthode accessible à l'extérieur de la classe.
- `private` : permet de rendre l'attribut ou la méthode uniquement accessible à l'intérieur de la classe.
- `protected` : permet de rendre l'attribut ou la méthode uniquement accessible à l'intérieur de la classe et à l'intérieur des classes filles.
