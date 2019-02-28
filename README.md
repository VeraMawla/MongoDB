# MongoDB Tutorial
MongoDB est un système de gestion de base de données open source (SGBD) qui utilise un modèle de données orienté document. Elle est considérée comme une base de données NoSQL, car elle n’utilise pas le modèle relationnel et n’utilise donc pas SQL comme langage de requête.

Une base de données MongoDB est différente d’une base de données relationnelle en ce sens que MongoDB utilise un modèle orienté document pour stocker les données. Dans le modèle orienté document, les données sont stockées dans les documents d'une collection. Dans le modèle relationnel, les données sont stockées dans des lignes d'une table.


# Les « Collections » 
Dans MongoDB, une Collection est un groupe de documents. Une Collection contient généralement des documents ayant un sujet similaire (utilisateurs, produits, publications, etc.).

Les collections ressemblent donc, à bien des égards, aux tables du modèle relationnel.

# Les « Documents »  
Dans MongoDB, les documents sont stockés sous forme de documents JSON. JSON (JavaScript Object Notation) est une norme qui facilite l'échange de données. Les documents JSON sont similaires aux documents XML en ce sens que les données peuvent être présentées de manière hiérarchique et peuvent être lues par les humains et les ordinateurs.

Voici un exemple de document JSON. Voici à quoi ressemblent les documents d’une base de données MongoDB.
```java
{
    CarCompany: "Renault",
    cars : [
                {
                    car : "Megan",
                    year : 2006,
                    color : "Black"
                }, 
                {
                    car : "Duster",
                    year : 2017,
                    color : "Orange"
                }
            ]
}
```
Le champ _id est l'identifiant unique d'un document. MongoDB permet de récupérer / référencer chaque document à l’aide de ce champ. Vous pouvez le fournir ou laisser MongoDB le générer.

En utilisant JSON, les résultats de requête peuvent être facilement analysés, avec peu ou pas de transformation, directement par JavaScript et les langages de programmation les plus courants. Cela est dû au fait que les documents JSON utilisent les conventions nom / paire et tableau qui sont familières aux langages de programmation les plus courants tels que C, C ++, C #, Java, JavaScript, Perl, Python et bien d’autres.


## h2

* liste1
* liste2
  * sous lise
  * sous liste2
  
  
1. numer1
1. number 2
1. number 3
   1.2 toto
   1.3 titit
   
   
```java
public class X {
   int m() {
       return ;
   }
}
```

> un encadré
> de plus

[Cofares](http://www.cofares.net)


