# Cours Java

## 1. Variables
- `int <nom> = <entier>;`
  - int est utilisé pour déclarer des variables qui contiennent des **entiers**
- `double <nom> = <flottant>;`
  - double est utilisé pour déclarer des variables qui contiennent des **flottants**
- `String <nom> = <texte>;`
  - String est utilisé pour déclarer des variables qui contiennent du **texte**
- `final <type> <nom> = <valeur>;`
  - final indique que c'est une **constante**
- `float <nom> = <flottant>;`
  - float est utilisé pour déclarer des variables qui contiennent des **flottants ayant jusqu'à 7 décimales** après la virgule, le reste sera perdu, d'où l'utilisation du type **double** qui n'a pas de limite

Lorsqu'on appelle une variable, on peut changer son type en mettant son nouveau type entre parenthèses avant d'appeler la fonction.

### Exemple :
```java
int a = 10;
int b = 4;
double c = a/(double)b;
```
-> $\mathrm c = 2,5$ car $\mathrm c$ est un flottant.

### Attention :
Lorsqu'on fait **a=b**, cela créer une copie de b dans a et non un raccourci

- `// <texte>`
  - un commentaire
- `/** <texte> */`
  - commentaire de documentation, permet la création d'un Javadoc (page web HTML) contenant la doc du code

On peut **concaténer** plusieurs chaînes de caractères et variables contenant du texte avec **+** (contrairement à **,** en Python).

On peut aussi concaténer des chaînes de caractère avec des nombres tant que le type de la variable auquel on assimile tout ça est un `String`.

- `Static <variable / méthode / classe>`
  - accessible dans Main

## 2. Hello World!
```java
package hello;

/**Ceci est une implémentation du message traditionnel "Hello World!"
*@autor L'équipe Education d'OpenClassroom
*/

public class HelloWorld{ //classe nommée HelloWorld et délimitée par {}

    //Le programme commence ici
    public static void main(String[]args){ //classe utilisée par l'interpréteur Java lors du démarrage d'un programme
        System.out.println("Hello World!"); //affiche le texte entre les parenthèses
    } //fin de la class main

} //fin de la class HelloWorld
```

Pour exécuter un programme Java, il faut d'abord le compiler :
- Ouvrir le terminal
- Utiliser `cd eclipse-workspace` puis `cd <nom du dossier>`
- Compiler le code en .class avec `javac <nom du fichier>.java` (convertit Java en Bytecode)
- Utiliser `cd ..` pour retourner dans la racine d'Eclipse
- Exécuter le code avec `javac <nom dossier>.<nom du fichier sans .class>`

## 3. Classes et fonctions
- `public class <nom> {<méthodes>}`
  - classe
- `public static void <nom> (<arguments>){<contenu>}`
  - fonction / méthode
- `public static void main (Sting[] args){}`
  - fonction principale (dite **fonction main**)

### Attention :
Aucun code n'est écrit en dehors d'une classe, ce qui signifie que **toutes les fonctions sont des méthodes en Java**.

- `return <variable>;`
  - retourne la valeur de la variable
- `@Override`
  - la fonction en dessous est redéfinie

## 4. Niveau de contrôle
En java, vous devez utiliser un des mots clés aux classes, variables et méthodes pour désigner un niveau de contrôle :
- `public`
  - visible pour tous
- `protected`
  - visible pour le package(ensemble de classes liées entre elles) et l'ensemble de ses sous-classes
- `package-protected`
  - généralement visible uniquement par le package dans lequel il se trouve (paramètres par défaut)
- `private`
  - accessible uniquement à l'intérieur de la classe dans laquelle il est situé

### Attention :
Le niveau de contrôle des classes et des méthodes influent celui de leur contenu.

### Exemple :
```java
public class PublicClass{
  public int zéro = 0;    //publique
  int un = 1;             //publique
  private int deux = 2;   //privé
}
```

## 5. Les boucles
- `for(<initialisation> ; <terminaison> ; <incrément>){<liste de déclaration>}`
  - boucle de dénombrement

  ### Exemple :
  ```java
  for(int i = 0 ; i < 5 ; i++){} //boucle de 5 tours
  ```
- `<variable>.length`
  - nombre d'éléments contenu dans la variable

  ### Exemple :
  ```java
  int[] myArray = new int[] {7, 2, 4}; //myArray.length = 3

  for(int number: myArray){} //la variable number va être égale à une des valeurs de myArray à chaque tours
  ```

- `while(<condition>){}`
  - boucle conditionnelle
  - conditions : >, =>, <, <=, ==, !=
- `do{<instruction>} while(<condition>)`
  - boucle conditionnelle où le test est fait à la fin, donc il y a au moins un tour de boucle
- `continue;`
  - lance un nouveau tours en interrompant celui-ci
- `break;`
  - stoppe la boucle et sort de la boucle

  ### Exemple :
  ```java
  for(int i = 0 ; i < 10 ; i++){
    if(i == 3){
      continue;
    } //quand i = 3 alors "Hello World!" n'est pas affiché et un nouveau tour commence
    if(i == 8){
      break;
    } //quand i = 8 alors "Hello World!" n'est pas affiché et la boucle for s'arrête
    System.out.println("Hello World!");
  }
  ```

## 6. Les classes
- `class <nom>{<contenu>}`
  - le contenu représente les différentes variables prises en compte par la classe

Les **attributs** (aussi appelés **champs** en Java) sont les variables que vous définissez quand vous créez une variable.

Pour instancier un objet, vous déclarez une variable de cette classe.

Quand vous instanciez un objet de cette classe, vous définissez également la valeur de chaque champ de cet objet.

### Exemple :
```java
class Book{ //nom de la classe / type
  String title;
  String author;
  int numberOfPages;
  String publisher = "OC"; //cette variable sera toujours égale à "OC"
} //ensemble des valeurs qui définissent la classe

Book myBook = new Book("Coding is art", "Becky James", 425); //entre parenthèses sont les valeurs des champs
myBook.title = "Coding is art";
myBook.author = "Becky James";
myBook.numberOfPages = myBook.numberOfPages + 10; //on peut modifier les valeurs
```

## 7. Héritage d'une classe
### Exemple :
```java
class FigureGeo{<contenu>};               //classe Mère

class Carre extends FigureGeo{<contenu>}; //classe Fille
```

L'héritage de la classe Mère "FigureGeo" dans la classe Fille "Carre" est dû au mot clé `extends` qui permet d'ajouter les variables et méthodes de FigureGeo dans Carre, participant alors à la spécialisation.

- **classe dérivée = classe fille**
- **classe de base = classe mère**

On peut aussi modifier une méthode de la classe de base si besoin en la redéfinissant dans la classe dérivée (**surcharger les méthodes**, cf polymorphisme).

## 8. Condition
- `if(<condition 1>){<contenu 1>}`

  `else if(<condition 2>){<contenu 2>}`
 
  `else{<contenu 1>}`

  - condition est de type **booléen** : `true` ou `false`
  - `$$` = and
    - entre 2 conditions
  - `||` = or
    - entre 2 conditions
  - `!` = not
    - avant une condition

Il y a aussi l'expression `switch` qui simplifie le code en remplaçant `if/else`.

### Exemple :
```java
switch(binaire){ //"binaire" est un entier égal à 0 ou 1
  case 0:        //"case" sert de test avec la variable placé entre parenthèses
    //code
    break;       //si on ne veut que avoir une seule solution, il faut utiliser l'instruction "break"
  case 1:
    //code
    break;
}
```

Dans le cas où il est possible qu'il y ait d'autres solutions, aboutissant toutes sur la même instruction, il faut utiliser `default;` après le dernier `case ... ;` pour avoir un cas où le résultat de l'expression ne correspond à aucun cas.

## 9. Tableaux
- `<type>[] <nom> = new <type>[<nombre d'éléments>];`
  - **création** d'un tableau
- `<nom d'un tableau>[<index>] = <valeur>;`
  - **ajout** d'une valeur dans l'index du tableau
- `<nom d'un tableau>[index];`
  - **retourne** la valeur présente à cet index
- `<nom> = new <type>[]{<élément 1>,<élément 2>,\dots,<élément n>};`
  - **ajout** des différents éléments du tableau

### Attention :
- Lors de la création d'un tableau d'entier, **toutes les valeurs sont égales à 0**
- L'argument de la fonction `main` est un tableau de chaînes de caractères, il est possible de le définir lors de l'exécution du programme en mettant l'argument après le nom du programme avec un espace : `java <nom du dossier>/<nom du programme> <arguments>`

### Matrice
- `<type>[][] <nom> = new <type>[nombre d'éléments][nombre d'éléments];`
  - création d'une **matrice** (tableau multidimensionnel)

### Attention :
On ne peut pas modifier le nombre d'éléments d'un tableau. C'est pourquoi il existe les listes, auxquels on peut modifier le nombre d'éléments : `List<<Paramètre de type>> <nom> = new ArrayList <<Paramètre de type>>();` (chevrons réels autour des Paramètres de type)

### Paramètre de type
- `Double` (double)
- `Boolean` (boolean)
- `Float` (float)
- `Integer` (int)
- `String`

### Manipulations sur une liste
- `.add(<élément>);`
  - **ajouter** l'élément à la fin de la liste
- `.add(<index>,<élément>);`
  - **ajouter** l'élément à l'index précisé, décalant toutes les valeurs à partir de cet index d'un vers la fin
- `.set(<index>,<élément>);`
  - **remplace** la valeur de l'index par le nouvel élément
- `.remove(<index>);`
  - **supprime** la valeur de l'index, décalant tous les éléments après l'index d'un vers l'avant
- `.size();`
  - **retourner** le nombre d'élément présents dans la liste

### Ensemble
- `Set<<Paramètre de type>><nom> = new HashSet<<Paramètre de type>>();`
  - **création** d'un ensemble

### Manipulations sur un ensemble
- `.add(<élément>);`
  - **ajouter** un élément (il n'y a pas d'index)
- `.remove(<élément>);`
  - **supprimer** l'élément
- `.size();`
  - **retourner** le nombre d'éléments présents dans l'ensemble

### Dictionnaires :
- `Map<<Paramètre de type de clé>,<Paramètre de type de valeur>> <nom> = new HashMap <<Paramètre de type de clé>,<Paramètre de type de valeur>>();`
  - **création** d'un dictionnaire

### Manipulations sur un dictionnaire
- `.put(<clé>,<valeur>);`
  - **ajout** de la clé associée à la valeur dans le dictionnaire
  - permet aussi de **modifier** une clé déjà existante
- `.get(<clé>);`
  - **retourner** la valeur associé à cette clé
- `.remove(<clé>);`
  - **supprimer** la clé et la valeur du dictionnaire
- `.size();`
  - **retourner** le nombre d'éléments présents dans le dictionnaire

## 10. Débuggage

### Erreurs de **compilation** :
- erreurs syntaxiques (fautes d'orthographe)
- erreurs sémantiques (mots interdits / code non interprétable / types incorrects)
  - ces 2 types d'erreurs sont averties grâce aux IDE (Eclipse)

### Erreurs **d'exécution** :
- erreurs de logique du code (erreurs de valeur ne provoquant pas de crash)
- erreurs de logique métier (erreurs provoquant un plantage / crash de l'application)

### Solutions :
- `try{<code pouvant générer une erreur>}`
  - s'il y a un problème dans ce code, alors une erreur / exception est générée (**throw**) et est capturée (**catch**)
- `catch(<exception> e){<code>};`
  - si l'erreur capturée correspond à l'exception, alors ce code est utilisé

## Attention :
Si aucune exception capturée ne correspond, alors il y a un crash.

### Exemples d'exception :
- `NumberFormatException`
- `ArithmeticException`

## 11. Lambda

Lambda est une **redéfinition** de l'unique **méthode** d'une interface fonctionnelle.

Une **interface fonctionnelle** est une classe n'ayant qu'**une seule méthode** :
- `public interface <nom>{<variable>};`
- `(<liste de paramètre>) -> <corps de la fonction>`
  - lambda
  - la liste de paramètre correspond aux :
    - arguments
    - indication des type (non obligatoire)
  - le corps de la fonction est entre `{}` s'il n'y a qu'une expression courte

Si il y a une **valeur qui est calculée** dans la méthode lambda, alors celle-ci sera **retournée** (s'il y en a plusieurs, alors c'est la dernière).

### Attention :
Si **aucune valeur** est calculée dans la méthode lambda, alors la valeur `void` **est retournée**.