# Appli_pire2pire
Application pire2pire - Utilise la methode Merise


## Table des matières

1. Introduction
2. Acronyme MERISE 
3. regles de gestions
4. Dictionnire de données
5. MCD
6. MLD
7. MPD
8. ScriptSQL

## 1/Introduction

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



## 2/ Acronymre MERISE


# Méthode Merise : Une approche structurée pour la conception de systèmes d'information

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

