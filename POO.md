# Object-Oriented-Programming (OOP) - Programmation Orientée Objet (POO) - ex. Java


## Définition - Que signifie "objet" en Java ?


Un objet Java est une combinaison de données et de procédures qui manipulent les données disponibles. Les objets ont un état et un comportement. L'état d'un objet est stocké dans des champs (variables ou attributs) et des méthodes (fonctions) représentent le comportement de l'objet. Les objets sont créés à partir de modèles appelés classes. En Java, les objets sont créés avec le mot clé "new".

## Qu’est ce qu’un objet?

C’est une unité de base de la programmation orientée objet et représente les entitées de la vie réelle. Un programme Java typique crée de nombreux objets qui interagissent en appelant des méthodes. 

Un objet est composé :
	
- Etat : Il est représenté par les attributs d’un objet.
- Comportement : Il est représenté par les méthodes d’un objet.
- Identité : Attribue un nom unique à un objet et permet à un objet d’interagir avec d’autres objets.

## Création d'objet


La création d'un objet est appelée instanciation car un objet est une instance d'une classe. Cette instanciation se fait à l'aide de l'opérateur new, suivi du nom de la classe à instancier et de parenthèses contenant les paramètres d'instanciation (ou parenthèses vides s'il n'y a pas de paramètres).

```java
class Personne{
	int age;
	int taille;
	int poids;
}
```

L'instanciation de cette classe se fait de la façon suivante : 

```java
new Personne();
```

Les classes et les objets sont les composants fondamentaux de la POO (Programmation Orientée Objet). Il y a souvent une confusion entre les classes et les objets. Comment vous expliquer la différence entre classe et objet?
 
 
Le concept d’utilisation de classes et d’objets consiste à encapsuler l’état et le comportement dans une seule unité de programmation. Les objets Java sont similaires aux objets du monde réel. Par exemple, nous pouvons créer un objet voiture en Java, qui aura des propriétés telles que la vitesse, la couleur actuelle et un comportement comme: Accélérer et Freiner.


## Qu’est ce qu’une classe?

Une classe est un plan ou un prototype défini par l’utilisateur à partir duquel des objets sont créés. Il représente l’ensemble des propriétés ou méthodes communes à tous les objets d’un type.

Exemple :

```java
public class Voiture {
  
     int vitesse;
     String model;
  
     public Voiture(String model) {
          this.model = model;
     }
  
     public void accelerer() {
          // ajoute 10 miles par heure à la vitesse actuelle
          vitesse = vitesse + 10;
     }
  
     public void freiner() {
          // déduire 10 miles par heure à la vitesse actuelle    
          vitesse = vitesse - 10;
     }
}
```

Regardez le code ci-dessus. Les états (vitesse et model) sont stockés dans des attributs et le comportement de l’objet (accélérer et freiner) est indiqué via des méthodes. Dans cet exemple, les méthodes sont accélérer() et freiner().

<img src="https://pasteboard.co/8YiimK7JzuPE.png" alt="Car Exemple">


## Noms de la classe

Lorsque vous créez une classe java, vous devez suivre cette règle: le nom du fichier et le nom de la classe doivent être les mêmes. Dans notre exemple, la classe « Voiture » doit être stockée dans un fichier nommé "Voiture.java". 
Java est également "case sensitive": Voiture écrit avec un "V" majuscule n’est pas la même chose que voiture écrit avec un "v" minuscule.

## Constructeur "Builder" de la classe Java

Les constructeurs ou "Builder" sont des méthodes spéciales. Celles-ci sont appelées lorsque nous créons une nouvelle instance de l’objet. Dans notre exemple ci-dessus, le constructeur est:

```java
public Voiture(String model) {
  this.model = model;
}
```

Les constructeurs doivent avoir le même nom que la classe elle-même. Ils peuvent prendre des paramètres ou non. Le paramètre dans cet exemple est « model ». Nous créons un nouvel objet voiture en utilisant ce constructeur comme ceci:

```java
Voiture renault = new Voiture("Renault");
```

Continuons maintenant avec notre exemple de voiture. Nous allons créer une deuxième classe nommée « VoitureExemple » et la stocker dans un fichier nommé VoitureExemple.java

```java
public class VoitureExemple {
  
  public static void main(String[] args) {

    //crée une nouvelle voiture Renault
    Voiture renault = new Voiture("Renault");

    //crée une nouvelle voiture Peugeot
    Voiture peugeot = new Voiture("Peugeot");
        
    //appelle la méthode d'accélération sur Renault
    renault.accelerer();
    
    //appelle la méthode d'accélération sur Peugeot
    peugeot.accelerer();
    
    //maintenant freiner la voiture Renault
    renault.freiner();

  }
}
```

Dans le code ci-dessus, nous avons crée deux nouveaux objets de type voiture : Renault et Peugeot. Il s’agit de deux instances distinctes de la classe Voiture (deux objets différents) et l’appel des méthodes de l’objet Renault n’affecte pas l’objet Peugeot.

### Conclusion

La classe Java est une entité qui détermine le comportement d’un objet et son contenu. Alors qu’un objet est un composant autonome composé de méthodes et de propriétés permettant de rendre utile certains types de données.

## Encapsulation

L’encapsulation est un mécanisme consistant à rassembler les données et les méthodes au sein d’une structure en cachant l’implémentation de l’objet, c’est-à-dire en empêchant l’accès aux données par un autre moyen que les services proposés. L’encapsulation permet donc de garantir l’intégrité des données contenues dans l’objet. Ainsi, si l’on veut protéger des informations contre une modification inattendue, on doit se référer au principe d’encapsulation.

L’encapsulation permet de définir des niveaux de visibilité des éléments de la classe. Ces niveaux de visibilité définissent les droits d’accès aux données selon que l’on y accède par une méthode de la classe elle-même, d’une classe héritière, ou bien d’une classe quelconque. Il existe quatre niveaux de visibilité :

- Visibilité par défaut : aucun modificateur de visibilité n’est indiqué.
- Visibilité publique : les fonctions de toutes les classes peuvent accéder aux données ou aux méthodes d’une classe définie avec le niveau de visibilité « public ». Il s’agit du plus bas niveau de protection des données.
- Visibilité protégée : l’accès aux données est réservé aux fonctions des classes héritières, c’est-à-dire par les fonctions membres de la classe et des classes dérivées. Ainsi, Un attribut ou une méthode déclarée « protected » est accessible uniquement aux classes d’un package et à ses sous-classes même si elles sont définies dans un package différent.
- Visibilité privée : l’accès aux données est limité aux méthodes de la classe elle-même. Il s’agit du niveau de protection des données le plus élevé


## Associations

Des relations peuvent être définies entre des objets. Lorsque l'on programme en orienté objet, nous mettons en relation des briques. 
L'association est donc la mise en relation de deux classes afin que l'une profite des fonctionnalités de l'autre. 
Lorsque des classes sont associées, elles sont couplées entre elles. 
Il est possible de multiplier les associations. 

## Agrégations et composition

L'agrégation et la composition sont deux types de relation. 

Dans l'agrégation, il y a une notion d'appartenance. Un objet appartient à un autre, mais la suppression de l'un ou de l'autre n'entraîne pas la disparition de l'objet restant. Les deux peuvent "vivre" indifféremment. 

Dans la composition, un objet ne peut subsiter sans l'autre. Par exemple un objet de Salaire fait partie d'un objet d'employé. Si l'employé disaparaît, son salaire aussi. 

## Généralisation et spécialisation des classes

La généralisation, c'est créer une superclasse qui contiendra plusieurs classes aux caractéristiques similaires. 

Dans l'autre sens, la spécialisation c'est créer des classes spécifiques à partir d'une classe mère. 
Par exemple, d'une classe voiture on crée une classe pneu. 

## Héritage

Le concept d'héritage est un des concepts les plus importants de la programmation orientée objet, car il conditionne irréversiblement la façon selon laquelle un code Java est écrit. L'héritage est un mécanisme permettant de créer une nouvelle classe à partir d'une classe existante en lui proférant ses propriétés et ses méthodes.

Ainsi, pour définir une nouvelle classe, il suffit de la faire hériter d'une classe existante et de lui ajouter de nouvelles propriétés/méthodes.

De cette façon, les classes héritées forment une hiérarchie descendante, au sommet de laquelle se situe la classe de base (superclasse). On appelle également la classe héritée la sous-classe et la classe parente la super-classe. 


## Classes abstraites et concrètes

Une classe abstraite est une classe qui ne sera pas utilisée comme telle. Elle possèdes des attributs et méthodes destinés à être accessibles aux classes tirées de celle-ci. 

Les classes concrètes sont justement celles tirées des classes abstraites (des superclasses), elles sont celles "réelles", utilisées et instanciées dans le programme. 

## Polymorphisme

Le polymorphisme est un mécanisme important dans la programmation objet. Il permet de modifier le comportement d’une classe fille par rapport à sa classe mère. Le polymorphisme permet d’utiliser l’héritage comme un mécanisme d’extension en adaptant le comportement des objets.



