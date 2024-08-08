# Appli_pire2pire
## Application pire2pire - Utilise la methode Merise


## Table des matières

1. [Introduction](#introduction)
2. [MERISE](#accro)
3. [Règles de gestion](https://github.com/Jwell2014/Appli_pire2pire/blob/master/Merise/Gestion_rules.md)
4. [Dictionnire de données](https://github.com/Jwell2014/Appli_pire2pire/blob/master/Merise/Dictionnaire_de_donnees.md)
5. [MCD](https://github.com/Jwell2014/Appli_pire2pire/blob/master/Merise/MCD.md)
6. [MLD](https://github.com/Jwell2014/Appli_pire2pire/blob/master/Merise/MLD.md)
7. [MPD](https://github.com/Jwell2014/Appli_pire2pire/blob/master/Merise/MPD.md)
8. [ScriptSQL](https://github.com/Jwell2014/Appli_pire2pire/blob/master/Merise/SciptSQL.md)
9. [UML](#uml)
10. [Use Case](https://github.com/Jwell2014/Appli_pire2pire/blob/master/UML/1.Use_case.md)
11. [Diagramme d'activité "Connection"](https://github.com/Jwell2014/Appli_pire2pire/blob/master/UML/2.Diagramme_activite_connection.md)
12. [Diagramme d'activité "Inscription formation"](https://github.com/Jwell2014/Appli_pire2pire/blob/master/UML/3.Diagramme_activite_inscription_formation.md)
13. [Diagramme de séquence "Connection"](https://github.com/Jwell2014/Appli_pire2pire/blob/master/UML/4.Diagramme_sequence_connection.md)
14. [Diagramme de séquence "Inscription formation"](https://github.com/Jwell2014/Appli_pire2pire/blob/master/UML/5.Diagramme_sequence_inscription_formation.md)








## 1/Introduction <a name="introduction"></a>

### **Contexte du projet**

Les formations sont organisés en modules.

Chaque module est caractérisé par un numéro de module sous forme de **Semantic Versionning**, un intitulé, un objectif pédagogique, un contenu (textes, images et vidéos), une durée en heures, un ou plusieurs tags et un auteur.

Un module peut faire partie d'une ou plusieurs formations, comme par exemple un pire module "**Commandes de base Git**" pourrait faire partie d'une pire formation "**Frontend Javascript**" et "**DevOps**", voir  plus.

Un module peut contenir un texte et/ou une image et/ou une vidéo.

Les apprenants peuvent s'inscrire à une ou plusieurs formations, ils peuvent choisir de ne pas suivre certains des modules s'ils possèdent déjà, par exemple, les compétences. Autrement dit, ils peuvent arbitrairement valider les modules de leur choix en un clic.

Chaque apprenant est évalué pour chaque module et possède un état de fin de module (OK / KO).

Une formation est considérée comme terminée lorsque tous les modules ont été validés.

Chaque apprenant est caractérisé par un numéro d’inscription unique, un nom, un prénom, une adresse et une date de naissance.

Un formateurs est auteur d'un module pour une formation donnée, chaque formateur est caractérisé par un code, un nom, un prénom.

### **Modalités pédagogiques**

Travail en groupe

Rendu individuel

Livraison Lundi 27 Mai 2024 09h

### **Modalités d'évaluation**

Revue des diagrammes sur le dépôt Git.

### **Livrables**

Un dépôt Github recensant : 

- Un README explicite et soigné 
- Une définition de l'acronyme MERISE dans le README.md 
- Un dictionnaire de données 
- Des règles de gestion 
- Un MCD
- Un MLD 
- Un MPD 
- Un script SQL de la base de données

### **Critères de performance**

La nomenclature MERISE est respectée
- Le méthode MERISE est respectée dans sa structure en découpant la conception de cette base de données en 3 niveaux : le niveau conceptuel, le niveau logique ou organisationnel, le niveau physique



## 2/ Acronymre MERISE <a name="accro"></a>

> MERISE (Méthode d'Etude et de Réalisation Informatique pour les Systèmes d'Entreprise) est une méthodologie de modélisation des données largement utilisée dans le domaine de l'informatique de gestion, en particulier en France.

## Méthode Merise : Une approche structurée pour la conception de systèmes d'information

La méthode Merise est une approche de conception de systèmes d'information largement utilisée dans le domaine de l'informatique et de la gestion de projets. Développée en France dans les années 1970 par René Colletti et Jean-René Bernard, cette méthode repose sur des concepts structurés et des démarches systématiques pour analyser, concevoir et implémenter des systèmes d'information.

## Principes fondamentaux de la méthode Merise

La méthode Merise se base sur trois principes fondamentaux :

1. **La séparation des données et des traitements** : Merise encourage à séparer clairement les données manipulées par le système (modèle conceptuel des données) et les traitements qui agissent sur ces données (modèle organisationnel).

2. **La modularité et la hiérarchisation** : Merise recommande de décomposer le système en modules fonctionnels, ce qui facilite la gestion du projet et permet une approche itérative du développement.

3. **La démarche ascendante et descendante** : Merise propose une démarche ascendante pour la conception (de l'analyse au détail) et une démarche descendante pour l'implémentation (du détail à la réalisation).

## Utilisation de la méthode Merise dans le projet Pire2Pire

Dans mon projet Pire2Pire, j'ai appliqué la méthode Merise pour concevoir et développer un système de gestion de formation en ligne. Voici comment j'ai utilisé la méthode Merise dans mon projet :

1. **Analyse des besoins et des contraintes** : j'ai commencé par analyser les besoins des utilisateurs ainsi que les contraintes techniques et fonctionnelles du projet. Cette phase a permis de définir les objectifs et les fonctionnalités du système.

2. **Modélisation conceptuelle des données** : En utilisant des outils de modélisation comme le modèle entité-association (MEA), j'ai représenté les principales entités et relations du domaine métier du projet. Cela m'a aidés à comprendre la structure des données manipulées par le système.

3. **Modélisation organisationnelle** : j'ai ensuite défini les différents processus et traitements du système, en identifiant les flux d'information et les règles de gestion associées. Cette étape m'a permis de décomposer le système en modules fonctionnels cohérents.

4. **Conception détaillée et implémentation** : En suivant une approche itérative, j'ai affiné les spécifications et conçu les interfaces utilisateur ainsi que les fonctionnalités du système. j'ai ensuite procédé à l'implémentation en utilisant des langages de programmation et des technologies adaptées.

En résumé, l'utilisation de la méthode Merise dans mon projet Pire2Pire m'a permis de structurer mon démarche de conception et de développement, en garantissant une meilleure compréhension des besoins des utilisateurs et une gestion efficace des risques et des contraintes du projet.


## 9/ Acronyme UML <a name="uml"></a>

**UML (Unified Modeling Language)** est une méthodologie standardisée utilisée pour modéliser des systèmes logiciels. Elle offre une représentation visuelle des éléments constitutifs d'un système et de leurs interactions, facilitant ainsi la conception, la documentation, et la communication au sein des équipes de développement.

## UML : Une approche standardisée pour la conception de systèmes logiciels

Le langage de modélisation UML a été développé dans les années 1990 par un groupe de chercheurs et d'ingénieurs, dont Grady Booch, Ivar Jacobson, et James Rumbaugh. UML est devenu un standard de facto pour la conception orientée objet, permettant de représenter aussi bien les aspects structurels que comportementaux d'un système logiciel.

## Principes fondamentaux d'UML

UML repose sur plusieurs concepts clés :

- **La modélisation structurelle et comportementale** : UML propose différents types de diagrammes pour modéliser la structure d'un système (diagrammes de classes, de composants, etc.) ainsi que son comportement (diagrammes de séquence, d'activité, etc.). Cela permet une vue complète et cohérente du système, facilitant sa conception et son implémentation.

- **L'abstraction et la modularité** : UML encourage l'utilisation d'abstractions pour simplifier la conception de systèmes complexes. Il permet de modéliser les composants du système de manière modulaire, facilitant ainsi la gestion des grands projets et la réutilisation des composants.

- **L'unification des méthodes de modélisation** : UML unifie plusieurs méthodes de modélisation préexistantes en un seul cadre cohérent. Cela permet aux développeurs et aux analystes de travailler avec une méthodologie commune, améliorant ainsi la collaboration et la communication au sein des équipes.

## Utilisation d'UML dans le projet Pire2Pire

Dans mon projet **Pire2Pire**, j'ai appliqué UML pour concevoir et développer un système de gestion de formation en ligne. Voici comment j'ai utilisé UML dans ce projet :

- **Analyse des exigences et définition des cas d'utilisation** : J'ai commencé par définir les exigences fonctionnelles en utilisant des diagrammes de cas d'utilisation. Cela m'a permis de capturer les interactions entre les utilisateurs et le système, ainsi que les fonctionnalités principales du système.

- **Modélisation des classes et des relations** : En utilisant un diagramme de classes, j'ai modélisé la structure statique du système, en définissant les classes principales, leurs attributs, méthodes, et relations. Cela m'a aidé à structurer les entités du domaine et à comprendre leur interconnexion.

- **Modélisation des interactions et des processus** : J'ai utilisé des diagrammes de séquence pour représenter les interactions entre les différents composants du système au fil du temps. Cela m'a permis de visualiser les échanges de messages entre les objets et de s'assurer que les processus critiques étaient correctement modélisés.

- **Modélisation des flux de travail** : Avec des diagrammes d'activité, j'ai décrit les processus métier et les flux de travail au sein du
