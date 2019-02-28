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
# Pas de Schéma
Chaque document JSON d'une collection peut contenir sa propre structure. Par conséquent, aucun schéma fixe ne limite le type de données pouvant être entrées dans une base de données MongoDB.

Ceci est en contraste avec une base de données relationnelle où vous devez d'abord créer le schéma (c'est-à-dire définir les tables, les colonnes, les types de données, etc.) avant de saisir des données. Si les données n'adhèrent pas au schéma, elles ne seront pas enregistrées dans la base de données.

# Installation
MongoDB peut être téléchargé et installé gratuitement à partir du site Web MongoDB : https://www.mongodb.com/download-center/community

# Conditions préalables
## Plate-forme
MongoDB nécessite une architecture x86-64 et supporte les versions suivantes:

    Windows 7 / Server 2008 R2
    Windows 8/2012 R2 et versions ultérieures

Pour L’installation :
Téléchargez le fichier d'installation de MongoDB à partir de la section Téléchargements du site Web MongoDB.

Recherchez le fichier .msi téléchargé dans l’explorateur Windows. Double-cliquez sur le fichier et suivez les instructions pour installer Mongo. Remarque: à moins que vous ne spécifiiez un répertoire personnalisé, Mongo est probablement installé dans le répertoire C: \ mongodb **. Toutefois, en fonction des paramètres de votre machine, Mongo peut être installé à d’autres emplacements. Par exemple, C: \ Program Files \ MongoDB \ Server \ 3.2. De plus, vous pouvez trouver MongoDB dans le menu Ajout / Suppression de programmes.

Créez le répertoire où MongoDB stockera ses fichiers. À partir de l'invite de commande, exécutez md \ data \ db. C'est l'emplacement par défaut. Cependant, d'autres emplacements peuvent être spécifiés à l'aide du paramètre --dbpath. Voir la documentation Mongo pour plus d'informations.

Démarrez le démon mongodb en exécutant C: \ mongodb \ bin \ mongod.exe dans l'invite de commande. Ou en exécutant C: \ path \ to \ mongodb \ bin \ mongod.exe

Se connecter à MongoDB à l'aide du shell Mongo Pendant l'exécution du démon MongoDB, à partir d'une autre fenêtre d'invite de commande, exécutez C: \ mongodb \ bin \ mongo.exe.


Vous pouvez accéder à MongoDB via le shell MongoDB ou à partir de votre environnement de programmation à l'aide d'un driver MongoDB.

Une fois que vous avez démarré une instance MongoDB (à l’aide de la commande mongod), vous pouvez maintenant vous connecter à cette instance et commencer à utiliser MongoDB.

Vous pouvez utiliser le terminal ou l'invite de commande de votre ordinateur pour vous connecter et exécuter des commandes directement à partir du shell MongoDB.

Vous pouvez également vous connecter à une instance MongoDB en cours d'exécution via votre environnement de programmation à l'aide d'un pilote MongoDB.

# MongoDB Shell (Mongo)
Tout au long de ce tutoriel, nous utiliserons le shell MongoDB (appelé mongo) pour vous connecter à notre instance en cours d'exécution MongoDB.

Le shell mongo est une interface JavaScript interactive pour MongoDB et il est inclus dans le package MongoDB. Vous pouvez utiliser le shell mongo pour interroger et mettre à jour des données, ainsi que pour exécuter des fonctions administratives.

Le shell MongoDB est situé au même endroit que les autres fichiers binaires. Pour l’exécuter, ouvrez une nouvelle fenêtre Invite de commandes / Terminal et entrez mongo (Linux / Mac) ou mongo.exe (Windows).

Cela suppose que le chemin a été ajouté à votre PATH. Si ce n'est pas le cas, vous devrez fournir le chemin complet.

# Connectez-vous à partir de votre environnement de programmation
Vous pouvez également vous connecter à MongoDB à partir de votre environnement de programmation.

Le site Web MongoDB contient une liste de pilotes MongoDB pouvant être utilisés pour se connecter à MongoDB.

Cette page contient des pilotes pour les langues suivantes:

    C
    C ++ (héritage)
    C ++ 11
    C #
    Java
    Node.js
    Perl
    PHP
    Python
    Moteur
    Rubis
    Scala

Une fois que vous êtes connecté au processus Mongod, vous pouvez créer une base de données.

# Créer une base de données
Dans MongoDB, vous créez une base de données en passant à une base de données inexistante, puis en y insérant des données.

Il n’existe pas d’instruction CREATE DATABASE dans MongoDB comme dans SQL. Pour créer une base de données dans MongoDB, passez simplement à une base de données inexistante, puis insérez-y des données.

Pour changer de base de données, exécutez l'instruction use. Si la base de données n'existe pas déjà, elle sera créée:
  
```java
use education
```

Cela entraîne le message suivant:

```java
switched to db education
```

Cependant, la base de données n'est réellement créée que lorsque vous y insérez des données:

```java
db.university.insert ({universityname: "CNAM"})
```

L'instruction ci-dessus crée une collection et y insère un document.

Il va générer le message suivant:

```java
WriteResult ({"nInserted": 1})
```

Vous pouvez voir la base de données dans votre liste de bases de données en lançant la commande suivante:
     
show databases

Voici un exemple de la sortie:

```java
car 0.000GB
education 0.000GB
homework 0.003GB
```

Dans ce cas, trois bases de données sont affichées, dont l'une est notre base de données nouvellement créée (education).

Vous pouvez également exécuter la ligne suivante pour afficher le contenu de votre base de données:

```java
db.education.find ()
```

Ce qui devrait produire une sortie comme ceci:

```java
{"_id": ObjectId ("5780fbf948ef8c6b3ffb0149"), "universityname": "CNAM"}
```

Comme vous pouvez le constater, notre paire nom / valeur est maintenant stockée dans la nouvelle base de données. MongoDB a également inséré un champ _id. Si vous ne fournissez pas de champ _id, MongoDB le fournit pour vous.

# Créer une Collection
Vous pouvez créer une collection à l'aide de la méthode createCollection () ou à la volée lorsque vous insérez un document.

Les collections sont comme des conteneurs pour les documents connexes. Ils sont généralement utilisés pour regrouper des documents d'un sujet similaire. Par exemple, vous pouvez avoir des noms de collection tels que utilisateurs, livres, publications, commentaires, etc.

Lorsque nous avons créé notre base de données, nous avons créé une collection appelée carCompany. Cette collection contiendra des documents avec les détails de car company, tels que les noms des voitures, les années, les couleurs, etc.

## Deux façons de créer une collection
Voici deux manières de créer des collections:

Vous pouvez créer une collection à la volée lors de l'insertion d'un document (à l'aide de la méthode insert ().

Vous pouvez également créer une collection de manière explicite à l'aide de la méthode createCollection().
    
### Avec insert()
Lorsque vous utilisez la méthode insert () pour insérer un document, vous spécifiez la collection dans laquelle le document sera inséré. Si la collection n'existe pas déjà, elle sera créée.

C'est la méthode que nous avons utilisée précédemment lorsque nous avons créé notre collection university lors de l'insertion d'un document.

Voici le code que nous avons utilisé:

```java
db.university.insert ({universityname: "CNAM"})
```

Dans ce cas, la collection university n'existait pas auparavant, elle a donc été créée pour nous.

### Avec createCollection()
Vous pouvez également créer des collections à l'aide de la méthode createCollection(). Cela vous permet de créer une collection sans insérer de document.

Voici un exemple d'utilisation de la méthode createCollection():

```java
db.createCollection ("university")
```

## Avec options

Vous pouvez également spécifier des options pour la collection à l'aide de la syntaxe db.createCollection(nom, options).

Voici un exemple:

```java
db.createCollection ("log", {limité: true, taille: 4500500, max: 4000})
```
# Créer un document
MongoDB fournit la méthode insert () (et deux autres) permettant d’ajouter des documents à une base de données.

MongoDB fournit les trois méthodes suivantes pour insérer des documents dans une base de données:

    insérer()
    insertOne ()
    insertMany ()

## La méthode insert ()
La méthode insert () insère un ou plusieurs documents dans une collection. Chaque document est fourni en paramètre. Le nom de la collection est ajouté à la méthode insert ().

Voici la syntaxe pour insérer un seul document:

```java
db.collectionName.insert ({name: "value"})
```

Dans l'exemple ci-dessus, le document est composé de {name: "value"}. Ceci est un document JSON. Les documents JSON consistent en une ou plusieurs paires nom / valeur, entourées d'accolades {}.

MongoDB utilise des documents JSON pour stocker des données, c'est pourquoi nous insérons des documents dans ce format.

Nous avons déjà utilisé cette méthode précédemment lorsque nous avons créé une base de données.

Ajoutons un autre document à notre base de données:

```java
db.university.insert ({universityname: "LIU"})
```

Ceci insère un document avec {universityname: "LIU"} comme contenu.

Maintenant, si nous recherchons la collection d'artistes, nous verrons deux documents (y compris celui que nous avons créé précédemment):

```java
db.university.find ()
{"_id": ObjectId ("5780fbf948ef8c6b3ffb0149"), "universityname": "CNAM"}
{"_id": ObjectId ("5781c9ac48ef8c6b3ffb014a"), " universityname ": "LIU"}
```

Notez que MongoDB a créé un champ _id pour les documents. Si vous n'en spécifiez pas, MongoDB en créera un pour vous. Cependant, vous pouvez fournir ce champ lors de l'insertion si vous préférez avoir le contrôle sur la valeur du champ _id.

```java
db.university.insert ({_id: 1, universityname: "AUB"})
```

Résultat:

```java
db.university.find ()
{"_id": ObjectId ("5780fbf948ef8c6b3ffb0149"), " universityname ": "CNAM"}
{"_id": ObjectId ("5781c9ac48ef8c6b3ffb014a"), " universityname ": "LIU"}
{"_id": 1, " universityname ": "AUB"}
```

## Créer plusieurs documents

Vous pouvez insérer plusieurs documents dans une même méthode insert ().

Dans cet exemple, nous insérons trois documents:

```java
db.university.insert (
   [
     {universityname: "MIT"},
     { universityname: "Oxford"},
     { universityname: "Berklee"}
   ]
)
```

Notez que les documents sont fournis sous forme de tableau. Les documents sont placés entre crochets [] et sont séparés par des virgules.

L'exécution du code ci-dessus entraîne le message suivant:

```java
BulkWriteResult ({
"writeErrors": [],
"writeConcernErrors": [],
"nInserted": 3,
"nUpserted": 0,
"nMatched": 0,
"nModified": 0,
"nRemoved": 0,
" upserted": []
})
```

## La méthode insertOne ()

Vous pouvez également utiliser la méthode insertOne() pour insérer un seul document dans une collection:

```java
db.university.insertOne ({_id: 1, universityname: "Oxford", country: "Britain"})
```

Ici, nous avons spécifié une collection inexistante. Comme avec la méthode insert (), la collection spécifiée sera créée si elle n'existe pas déjà.

Vous remarquerez que le résultat est différent de lorsque vous utilisez la méthode insert ():

```java
{" acknowledged ": true, "insertedId": 1}
```


## La méthode insertMany ()

Comme son nom l'indique, vous pouvez utiliser insertMany () pour insérer plusieurs documents:

```java
db.musicians.insertMany (
   [
     {_id: 2, nom: "Ian Paice", instrument: "Drums", né en 1948},
     {_id: 3, nom: "Roger Glover", instrument: "Bass", né: 1945},
     {_id: 4, nom: "Steve Morse", instrument: "Guitar", né en 1954},
     {_id: 5, nom: "Don Airey", instrument: "Claviers", né en 1948},
     {_id: 6, nom: "Jeff Martin", instrument: "Vocals", né en 1969},
     {_id: 7, nom: "Jeff Burrows", instrument: "Drums", né en 1968},
     {_id: 8, nom: "Stuart Chatwood", instrument: "Bass", né en 1969},
   ]
)
```

De nouveau, la sortie lors de l'utilisation de insertMany () est différente de celle obtenue si vous aviez inséré plusieurs documents à l'aide de la méthode insert ():

```java
{
" acknowledged ": true,
"InsertedIds": [
2
3
4
5
6
7,
8
]
}
```

## Faire une ‘Query’ Requête

MongoDB fournit la méthode db.collection.find () pour interroger les documents d'une collection.

```java
Db.collection.find () sélectionne les documents d'une collection et renvoie un curseur sur les documents sélectionnés.
```

### Renvoyer tous les documents

Cet exemple renvoie tous les documents de la collection de musiciens:

```java
db.musicians.find ()
```

Résultat:

```java
{"_id": 1, "name": "Ian Gillan", "instrument": "Vocals"}
{"_id": 2, "nom": "Ian Paice", "instrument": "Batterie", "né": 1948}
{"_id": 3, "nom": "Roger Glover", "instrument": "basse", "né": 1945}
{"_id": 4, "nom": "Steve Morse", "instrument": "Guitare", "né": 1954}
{"_id": 5, "nom": "Don Airey", "instrument": "Claviers", "né": 1948}
{"_id": 6, "name": "Jeff Martin", "instrument": "Vocals", "né": 1969}
{"_id": 7, "nom": "Jeff Burrows", "instrument": "Batterie", "né": 1968}
{"_id": 8, "nom": "Stuart Chatwood", "instrument": "Basse", "né": 1969}
```

Il renvoie tous les documents car nous n’avons passé aucun paramètre en tant que critère de filtrage.

## Ajouter des critères de filtrage

Vous pouvez filtrer les résultats en indiquant uniquement les critères qui vous intéressent.

Par exemple, si nous ne sommes intéressés que par AIU de la collection university:

```java
db.university.find ({universityname: "AIU"})
```

Résultat:

```java
{"_id": ObjectId ("5781f85d48ef8c6b3ffb0150"), "universityname": "AIU", "departments": [{"department": "Law", "Branch": “B1”, "Section": "A"} , {"department": "Informatics", "Branch": “B4”, "Section": "C"}]}
```

## Formater les résultats

Vous pourriez trouver les résultats ci-dessus un peu difficiles à lire. Le document est renvoyé sous la forme d'une longue ligne de texte.

Vous pouvez utiliser la méthode pretty() pour formater les résultats afin qu'ils soient un peu plus faciles à lire.

Ajoutez simplement pretty() à la fin, comme ceci:

```java
db.university.find ({universityname: "AIU"}).pretty()
```

Résultat:

```
{
"_id": ObjectId ("5781f85d48ef8c6b3ffb0150"),
"universityname": "AIU",
"departments": [
{
"department": "Law",
"Branch": “B1”,
"Section": "A"
},
{
"department": "Informatics",
"Branch": “B4”,
"Section": "C"
}
]
}
```

## Plus d'options de filtrage

Voici d'autres moyens de filtrer les résultats.

Spécifiez ET Conditions

Vous pouvez spécifier que seuls les documents contenant deux valeurs spécifiées ou plus doivent être renvoyés.

Dans cet exemple, nous spécifions que seuls les musiciens qui jouent de la batterie et qui sont nés avant 1950 doivent être renvoyés. Seuls les documents correspondant aux deux critères seront renvoyés.

```java
db.musicians.find ({instrument: "Drums", né le {$lt: 1950}})
```

Résultat:

```java
{"_id": 2, "nom": "Ian Paice", "instrument": "Batterie", "né": 1948}
```



## Spécifiez les conditions OU

Vous pouvez également spécifier que l'une ou l'autre valeur doit être vraie. Tant que l'une des conditions est vraie, le document sera renvoyé.

Dans cet exemple, nous voulons des documents contenant des musiciens jouant de la batterie ou nés avant 1950.

```java
db.musicians.find (
   {
     $ ou: [{instrument: "Drums"}, {né: {$ lt: 1950}}]
   }
)
```

Résultat:

```java
{"_id": 2, "nom": "Ian Paice", "instrument": "Batterie", "né": 1948}
{"_id": 3, "nom": "Roger Glover", "instrument": "basse", "né": 1945}
{"_id": 5, "nom": "Don Airey", "instrument": "Claviers", "né": 1948}
{"_id": 7, "nom": "Jeff Burrows", "instrument": "Batterie", "né": 1968}
```

## L'opérateur $in

L'opérateur $in vous permet de fournir une liste de valeurs. Si un document contient l'une de ces valeurs, il sera renvoyé.

À l'aide de l'exemple suivant, nous recherchons tous les musiciens qui chantent ou jouent de la guitare.

```java
db.musicians.find ({instrument: {$in: ["Vocals", "Guitar"]}})
```

Résultat :

```java
{"_id": 1, "name": "Ian Gillan", "instrument": "Vocals"}
{"_id": 4, "nom": "Steve Morse", "instrument": "Guitare", "né": 1954}
{"_id": 6, "name": "Jeff Martin", "instrument": "Vocals", "né": 1969}
```

## Interroger un tableau de documents
Cet exemple interroge un tableau de documents. Il trouve des albums qui ont été publiés après l'an 2000.

```java
db.artists.find (
   {
      albums: {
                $ elemMatch: {
                     année: {$ gt: 2000}
                }
      }
   }
).pretty()
```

Résultat:

```java
{
"_id": ObjectId ("578217c248ef8c6b3ffb015a"),
"universityname": "LAU",
"departments": [
{
"department": "Humanities",
"Branch": "B3",
"Section": "D"
},
{
"department": "Genie Civil",
"Branch": "B2",
"Section": "A"
}
]
}
{
"_id": ObjectId ("578217c248ef8c6b3ffb015b"),
"universityname": "Sorbone",
"departments": [
{
"department": "Nano Technology",
"Branch": "B5",
"Section": "B"
},
{
"department": "Mathematics",
"Branch": "B6",
"Section": "G"
}
]
}
```

Vous remarquerez que ces résultats contiennent également des albums antérieurs à 2000. C'est exact: c'est le fonctionnement des bases de données orientées document. Toute requête renvoie le document entier (mais uniquement les documents correspondant aux critères spécifiés).

## La méthode db.collection.findOne ()
Vous pouvez utiliser la méthode db.collection.findOne () pour renvoyer un document répondant aux critères de requête spécifiés.

Si plusieurs documents répondent aux critères, seul le premier est renvoyé, comme déterminé par l'ordre naturel des documents sur le disque.

Donc, en recherchant toute une collection comme celle-ci:

```java
db.musicians.findOne ()
```

## Renverra un seul document:

```java
{"_id": 1, "name": "Ian Gillan", "instrument": "Vocals"}
```

Si nous changeons le findOne () pour trouver () comme ceci:

```java
db.musicians.find ()
```
Nous voyons qu'il y a actuellement 8 documents dans la collection:

```java
{"_id": 1, "name": "Ian Gillan", "instrument": "Vocals"}
{"_id": 2, "nom": "Ian Paice", "instrument": "Batterie", "né": 1948}
{"_id": 3, "nom": "Roger Glover", "instrument": "basse", "né": 1945}
{"_id": 4, "nom": "Steve Morse", "instrument": "Guitare", "né": 1954}
{"_id": 5, "nom": "Don Airey", "instrument": "Claviers", "né": 1948}
{"_id": 6, "name": "Jeff Martin", "instrument": "Vocals", "né": 1969}
{"_id": 7, "nom": "Jeff Burrows", "instrument": "Batterie", "né": 1968}
{"_id": 8, "nom": "Stuart Chatwood", "instrument": "Basse", "né": 1969}
```

[MongoDB] (https://veramawla.github.io/MongoDB/)
