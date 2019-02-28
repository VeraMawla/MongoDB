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
  
    use education

Cela entraîne le message suivant:
     switched to db education

Cependant, la base de données n'est réellement créée que lorsque vous y insérez des données:

    db.university.insert ({universityname: "CNAM"})

L'instruction ci-dessus crée une collection et y insère un document.

Il va générer le message suivant:

   WriteResult ({"nInserted": 1})

Vous pouvez voir la base de données dans votre liste de bases de données en lançant la commande suivante:
     
show databases

Voici un exemple de la sortie:

car 0.000GB
education 0.000GB
homework 0.003GB

Dans ce cas, trois bases de données sont affichées, dont l'une est notre base de données nouvellement créée (education).

Vous pouvez également exécuter la ligne suivante pour afficher le contenu de votre base de données:

db.education.find ()

Ce qui devrait produire une sortie comme ceci:

{"_id": ObjectId ("5780fbf948ef8c6b3ffb0149"), "universityname": "CNAM"}

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

db.university.insert ({universityname: "CNAM"})

Dans ce cas, la collection university n'existait pas auparavant, elle a donc été créée pour nous.

### Avec createCollection()
Vous pouvez également créer des collections à l'aide de la méthode createCollection(). Cela vous permet de créer une collection sans insérer de document.

Voici un exemple d'utilisation de la méthode createCollection():

         db.createCollection ("university")

Avec options

Vous pouvez également spécifier des options pour la collection à l'aide de la syntaxe db.createCollection(nom, options).

Voici un exemple:

         db.createCollection ("log", {limité: true, taille: 4500500, max: 4000})

# Créer un document
MongoDB fournit la méthode insert () (et deux autres) permettant d’ajouter des documents à une base de données.

MongoDB fournit les trois méthodes suivantes pour insérer des documents dans une base de données:

    insérer()
    insertOne ()
    insertMany ()

## La méthode insert ()
La méthode insert () insère un ou plusieurs documents dans une collection. Chaque document est fourni en paramètre. Le nom de la collection est ajouté à la méthode insert ().

Voici la syntaxe pour insérer un seul document:

db.collectionName.insert ({name: "value"})

Dans l'exemple ci-dessus, le document est composé de {name: "value"}. Ceci est un document JSON. Les documents JSON consistent en une ou plusieurs paires nom / valeur, entourées d'accolades {}.

MongoDB utilise des documents JSON pour stocker des données, c'est pourquoi nous insérons des documents dans ce format.

Nous avons déjà utilisé cette méthode précédemment lorsque nous avons créé une base de données.

Ajoutons un autre document à notre base de données:

db.university.insert ({universityname: "LIU"})

Ceci insère un document avec {artistname: "Jorn Lande"} comme contenu.

Maintenant, si nous recherchons la collection d'artistes, nous verrons deux documents (y compris celui que nous avons créé précédemment):

> db.university.find ()
{"_id": ObjectId ("5780fbf948ef8c6b3ffb0149"), "universityname": "CNAM"}
{"_id": ObjectId ("5781c9ac48ef8c6b3ffb014a"), " universityname ": "LIU"}

Notez que MongoDB a créé un champ _id pour les documents. Si vous n'en spécifiez pas, MongoDB en créera un pour vous. Cependant, vous pouvez fournir ce champ lors de l'insertion si vous préférez avoir le contrôle sur la valeur du champ _id.

db.university.insert ({_id: 1, universityname: "AUB"})

Résultat:

> db.university.find ()
{"_id": ObjectId ("5780fbf948ef8c6b3ffb0149"), " universityname ": "CNAM"}
{"_id": ObjectId ("5781c9ac48ef8c6b3ffb014a"), " universityname ": "LIU"}
{"_id": 1, " universityname ": "AUB"}

