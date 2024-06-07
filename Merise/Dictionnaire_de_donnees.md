**Dictionnaire de données**

Un dictionnaire de données est un outil indispensable pour la gestion efficace des données, décrivant en détail la structure des bases de données. Il offre des informations précises sur les tables, les colonnes, les types de données et les contraintes, assurant ainsi une standardisation et une cohérence des données au sein de l'application.

Il constitue une référence essentielle pour les développeurs, les administrateurs de bases de données et les analystes, aidant à maintenir l'intégrité des données, à faciliter les modifications structurelles et à garantir la conformité aux réglementations.

Ce tableau présente chaque table avec ses attributs, types de données et clés primaires et étrangères, ainsi que des descriptions.

| Entité | Attribut | Type de Données | Longueur | Contraintes | Description | Exemple |
| --- | --- | --- | --- | --- | --- | --- |
| Roles | id_role | INT |  | AUTO_INCREMENT, NOT NULL, UNIQUE, PK | Identifiant unique du rôle | 1 |
|  | type | VARCHAR | 50 |  | Type de rôle | "Administrateur" |
| Adresses | id_adresse | INT |  | AUTO_INCREMENT, NOT NULL, UNIQUE, PK | Identifiant unique de l'adresse | 1 |
|  | numero | INT |  | NOT NULL | Numéro de l'adresse | 12 |
|  | rue | VARCHAR | 50 | NOT NULL | Rue de l'adresse | "Rue des Acacias" |
|  | ville | VARCHAR | 50 | NOT NULL | Ville de l'adresse | "Lyon" |
|  | code_postal | VARCHAR | 50 | NOT NULL | Code postal de l'adresse | "69001" |
|  | pays | VARCHAR | 50 | NOT NULL | Pays de l'adresse | "France" |
| Utilisateurs | id_utilisateur | INT |  | AUTO_INCREMENT, NOT NULL, UNIQUE, PK | Identifiant unique de l'utilisateur | 1 |
|  | nom | VARCHAR | 50 |  | Nom de l'utilisateur | "Durand" |
|  | prenom | VARCHAR | 50 |  | Prénom de l'utilisateur | "Emmy" |
|  | email | VARCHAR | 50 |  | Adresse e-mail de l'utilisateur | "mailto:emmy.durand@example.com" |
|  | mdp | VARCHAR | 50 |  | Mot de passe de l'utilisateur | "@p#as%J2R!" |
|  | date_de_naissance | DATE |  |  | Date de naissance de l'utilisateur | "1992-07-15" |
|  | id_adresse | INT |  | NOT NULL, FK | Clé étrangère vers la table Adresses | 1 |
| Paragraphes | id | INT |  | AUTO_INCREMENT, NOT NULL, UNIQUE, PK | Identifiant unique du paragraphe | 1 |
|  | nom | VARCHAR | 50 | NOT NULL | Nom du paragraphe | "Introduction" |
|  | contenu | TEXT |  | NOT NULL | Contenu du paragraphe | "Contenu du paragraphe..." |
| Videos | id_video | INT |  | AUTO_INCREMENT, NOT NULL, UNIQUE, PK | Identifiant unique de la vidéo | 1 |
|  | nom | VARCHAR | 50 | NOT NULL | Nom de la vidéo | "Vidéo d'introduction" |
|  | url | TEXT |  | NOT NULL | URL de la vidéo | "https://example.com/video.mp4" |
| Lecons | id_lecon | INT |  | AUTO_INCREMENT, NOT NULL, UNIQUE, PK | Identifiant unique de la leçon | 1 |
|  | nom | VARCHAR | 50 | NOT NULL | Nom de la leçon | "Introduction à Python" |
|  | contenu | TEXT |  | NOT NULL | Contenu de la leçon | "Détails sur les types de données..." |
|  | id_video | INT |  | NOT NULL, FK | Clé étrangère vers la table Videos | 1 |
| Images | id_image | INT |  | AUTO_INCREMENT, NOT NULL, UNIQUE, PK | Identifiant unique de l'image | 1 |
|  | nom | VARCHAR | 50 | NOT NULL | Nom de l'image | "Image d'introduction" |
|  | url | TEXT |  | NOT NULL | URL de l'image | "https://example.com/image.jpg" |
| Modules | id_module | INT |  | AUTO_INCREMENT, NOT NULL, UNIQUE, PK | Identifiant unique du module | 1 |
|  | nom | VARCHAR | 50 | NOT NULL | Nom du module | "Fondamentaux de la programmation" |
|  | contenu | TEXT |  | NOT NULL | Contenu du module | "Apprendre les bases de Python..." |
| Formations | id | INT |  | AUTO_INCREMENT, NOT NULL, UNIQUE, PK | Identifiant unique de la formation | 1 |
|  | titre | VARCHAR | 50 | NOT NULL | Titre de la formation | "Bases de Données" |
|  | contenu | TEXT |  | NOT NULL | Contenu de la formation | "Introduction aux Bases de Données" |
| Tag | id | INT |  | AUTO_INCREMENT, NOT NULL, UNIQUE, PK | Identifiant unique du tag | 1 |
|  | nom | VARCHAR | 50 | NOT NULL | Nom du tag | "#TypeScript" |
| Validation_lecons | id_validation_lecon | INT |  | AUTO_INCREMENT, NOT NULL, UNIQUE, PK | Identifiant unique de la validation de la leçon | 1 |
|  | nom | VARCHAR | 50 | NOT NULL | Nom de la validation de la leçon | "Validation de Python" |

### Relations et Contraintes

| Entité Source | Attribut Source | Entité Cible | Attribut Cible | Type de Contrainte |
| --- | --- | --- | --- | --- |
| ObjPedagogiques | id_module | Modules | id_module | FK |
| ObjPedagogiques | id | Formations | id | FK |
| ObjPedagogiques | id_lecon | Lecons | id_lecon | AK |
| Etre | id_lecon | Lecons | id_lecon | FK |
| Etre | id_validation_lecon | Validation_lecons | id_validation_lecon | FK |
| Lier_lecon | id_lecon | Lecons | id_lecon | FK |
| Lier_lecon | id | Tag | id | FK |
| Ecrire_lecon | id | Paragraphes | id | FK |
| Ecrire_lecon | id_lecon | Lecons | id_lecon | FK |
| Imager_lecon | id | Images | id | FK |
| Imager_lecon | id_lecon | Lecons | id_lecon | FK |
| Projeter_lecon | id_video | Videos | id_video | FK |
| Projeter_lecon | id_lecon | Lecons | id_lecon | FK |
| Remplir | id_module | Modules | id_module | FK |
| Remplir | id_lecon | Lecons | id_lecon | FK |
| Creer_lecon | id_lecon | Lecons | id_lecon | FK |
| Creer_lecon | id_utilisateur | Utilisateurs | id_utilisateur | FK |

