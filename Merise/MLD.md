# ** MLD **

La transition du MCD au MLD vise à convertir une représentation conceptuelle des données en une structure logique prête à être implémentée, tout en garantissant l'intégrité, la performance et la maintenabilité de la base de données.

Ce processus requiert une compréhension approfondie des besoins métier et des capacités du système de gestion de base de données choisi (PostgreSQL dans notre cas).

![Getting Started](/Assets/mld.png)

**Identification des Entités**

Chaque entité identifiée dans le Modèle Conceptuel de Données (MCD) est transformée en table dans le MLD, avec les attributs de chaque entité devenant les colonnes de ces tables. Par exemple, les entités `Utilisateur`, `Adresse`, `Role`, etc., sont toutes représentées avec des attributs spécifiques et des types de données adaptés à leurs fonctions.

**Clés Primaires Uniques (PK)**

Une clé primaire est assignée à chaque table, soit issue des attributs existants de l'entité, soit ajoutée spécifiquement pour servir d'identifiant unique.

**Clés Étrangères (FK)**

Les clés étrangères sont essentielles pour maintenir les relations d’intégrité référentielle entre les différentes tables de notre base de données. Elles permettent de lier les tables entre elles, assurant que les données sont cohérentes et correctes à travers les différentes entités.

**Avantages**

- **Maintenir l’intégrité référentielle** : Assure que des liens ne peuvent exister que si les données correspondantes existent.
- **Clarifier la structure relationnelle** : Rend les relations entre les entités explicites et facilement compréhensibles, facilitant ainsi les requêtes et la maintenance de la base de données.

**Normalisation - Respect de la 3ème Forme Normale (3NF)**

Les tables sont structurées pour éliminer la redondance et prévenir les anomalies de mise à jour, respectant les trois premières formes normales (1NF, 2NF et 3NF). Cela garantit l’intégrité, la cohérence et la simplicité de notre base de données, et semble suffisant pour notre application.

**Intégration des Contraintes d'Intégrité**

Les contraintes d'intégrité fonctionnelles et physiques comme l'unicité, les clés étrangères, et les validations sont mises en place pour garantir la validité et la sécurité des opérations sur les données.

**Optimisation des Performances par Indexation**

Des index sont prévus pour améliorer les performances des requêtes, particulièrement sur les colonnes fréquemment utilisées dans les recherches ou les jointures.