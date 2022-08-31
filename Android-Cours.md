# Android Studio

## Language
- Java
- Kotlin (nouveau langage officiel d'Android)

## Package name
- Définit le nom de l'application
- Permet de distinguer 2 apps avec le même nom
- Convention : com.nom_société.nom_app

## AndroidManifest.xml
Ce fichier est la carte d'identité de votre application. Il permet entre autres de préciser le nom de l'application, l'icône à utiliser, quelle activité lancer au démarrage, etc.

## Répertoire /res
Ce répertoire contient toutes les ressources de l'application, et comprend quatre sous-répertoires :
- le dossier `drawable`, qui contient l'ensemble des images et contenus à afficher à l'écran (par exemple une image de bouton, une icône ou un logo) ;
- le dossier `layout`, qui contient l'ensemble des fichiers layout de votre application ;
- le dossier `mipmap`, qui contient principalement l'icône de lancement de l'application ;
- le dossier `values`, qui contient différents paramétrages et valeurs, par exemple les couleurs à utiliser dans l'application, les différentes traductions de texte à utiliser ou les styles graphiques à appliquer.

## Activités
- Chaque écran différents est une activité
- Le nom est suivit de "Activity" et est écrit en CamelCase

## Layout
- En XML
- Définit tout ce qui est affiché à l'écran
- Situé dans res/layout
- Le nom est suffixé par activity et lié par "_", donc écrit en snake_case

### Conteneur
Pour afficher des éléments à l'écran, il est impératif d'utiliser un conteneur. Un conteneur est un élément particulier permettant d'organiser les éléments qu'il contient entre eux.

Dans le fichier XML de notre projet, le premier élément XML que nous voyons est du type androidx.constraintlayout.widget.ConstraintLayout. Cet élément est un conteneur. Android suffixe toujours le nom des conteneurs par Layout. Dans cet exemple, le conteneur contient un élément TextView, utilisé pour afficher le texte Hello World!.

Parmi les conteneurs proposés par Android, nous pouvons noter par exemple :
- `FrameLayout` : permet de positionner les éléments les uns au-dessus des autres ;
- `LinearLayout` : permet de positionner les éléments les uns à la suite des autres, dans le sens horizontal ou vertical ;
- `RelativeLayout` : permet de positionner les éléments les uns par rapport aux autres ;
- `ConstraintLayout` : comme le RelativeLayout, mais avec des règles de positionnement beaucoup plus puissantes.

# Test 1

## Question 1
Un fichier layout permet d'organiser l'affichage des différents éléments graphiques qui seront présentés à l'utilisateur, c'est-à-dire de définir la structure visuelle de l'interface utilisateur.

## Question 2
L'élément TextView permet d'afficher du texte. 

Attention, l'élément EditText permet quant à lui de récupérer du texte saisi par l'utilisateur.

## Question 3
Je suis en train de positionner mes widgets dans mon layout. Je souhaite donner un peu de marge à ma TextView pour qu’elle ne “colle” pas le layout parent. Quelles margins puis-je utiliser ? 8 et 4 dp. 

Le mieux serait d’utiliser 8 dp. C’est un peu l’espacement “par défaut” sur Android. Il est partout ! Mais 4 dp pourraient convenir aussi, si l’espacement doit être plus faible (entre un titre et un sous-titre, par exemple). En fait, le Material Design est conçu pour être utilisé sur une grille de 4 dp. Les tailles et espacements les plus adaptés sont donc 4 dp, 8 dp, 16 dp, etc. 

## Question 4
Sur Android, il y a uniquement les conteneurs `FrameLayout, LinearLayout, RelativeLayout et Constraint Layout`.

## Question 5
L'attribut XML à utiliser pour ajouter de l'espace autour d'un élément graphique (et non à l'intérieur) est layout_margin.

Les attributs layout_width et layout_height permettent de déterminer la largeur et la hauteur d'un élément par rapport à son conteneur. L'attribut padding permet de déterminer le rembourrage, c'est-à-dire l'espace entre le contenu d'un élément et ses bords intérieurs. L'attribut gravity permet de déterminer la position du contenu au sein de son élément.

## Question 6
La méthode permettant de référencer un élément graphique dans le code s’appelle findViewById().

La méthode getView() existe, mais elle ne sert pas à cela !

## Question 7
La méthode setOnClickListener permet d’intercepter le clic de l’utilisateur sur un bouton.

## Question 8
La classe Android qui centralise l’ensemble des identifiants de toutes les ressources du projet s'appelle la classe R.

Cette classe est générée automatiquement à chaque compilation du projet.