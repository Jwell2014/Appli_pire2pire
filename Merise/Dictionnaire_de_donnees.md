**Dictionnaire de données**

Un dictionnaire de données est un outil indispensable pour la gestion efficace des données, décrivant en détail la structure des bases de données. Il offre des informations précises sur les tables, les colonnes, les types de données et les contraintes, assurant ainsi une standardisation et une cohérence des données au sein de l'application.

Il constitue une référence essentielle pour les développeurs, les administrateurs de bases de données et les analystes, aidant à maintenir l'intégrité des données, à faciliter les modifications structurelles et à garantir la conformité aux réglementations.

Ce tableau présente chaque table avec ses attributs, types de données et clés primaires et étrangères, ainsi que des descriptions.

| Nom de la table | Description | Nom de l'attribut | Type de données | Clé | Description de l'attribut |
| --- | --- | --- | --- | --- | --- |
| Roles | Stocke les informations sur les rôles | Id_Role | Integer | PK | Identifiant du rôle |
|  |  | Libelle | String |  | Nom du rôle |
| Utilisateurs | Contient les informations des utilisateurs | Id_Utilisateur | Integer | PK | Identifiant de l'utilisateur |
|  |  | Nom | String |  | Nom de l'utilisateur |
|  |  | Prenom | String |  | Prénom de l'utilisateur |
|  |  | Email | String |  | Adresse email de l'utilisateur |
|  |  | Mot_de_passe | String |  | Mot de passe de l'utilisateur |
|  |  | Id_Role | Integer | FK (Roles) | Référence au rôle de l'utilisateur |
| Formations | Regroupe les informations sur les formations | Id_Formation | Integer | PK | Identifiant de la formation |
|  |  | Libelle | String |  | Nom de la formation |
|  |  | Description | String |  | Description de la formation |
| Projets_Formations | Table associative pour les projets et formations | Id_Video | Integer | PK, FK (Videos) | Référence à la vidéo liée au projet |
|  |  | Id_Formation | Integer | PK, FK (Formations) | Référence à la formation liée au projet |
| Videos | Contient les informations des vidéos | Id_Video | Integer | PK | Identifiant de la vidéo |
|  |  | Libelle | String |  | Nom de la vidéo |
|  |  | Nom | String |  | Fichier de la vidéo |
| Projets_Modules | Table associative pour les projets et modules | Id_Video | Integer | PK, FK (Videos) | Référence à la vidéo liée au projet |
|  |  | Id_Module | Integer | PK, FK (Modules) | Référence au module lié au projet |
| Projets_Images | Table associative pour les projets et images | Id_Video | Integer | PK, FK (Videos) | Référence à la vidéo liée au projet |
|  |  | Id_Image | Integer | PK, FK (Images) | Référence à l'image liée au projet |
| Images | Contient les informations des images | Id_Image | Integer | PK | Identifiant de l'image |
|  |  | Libelle | String |  | Nom de l'image |
| Paragraphes | Contient les informations des paragraphes | Id_Paragraphe | Integer | PK | Identifiant du paragraphe |
|  |  | Libelle | String |  | Titre du paragraphe |
|  |  | Contenu | Text |  | Contenu du paragraphe |
| Objets_Pedagogiques | Contient les informations des objets pédagogiques | Id_Objet | Integer | PK | Identifiant de l'objet pédagogique |
|  |  | Libelle | String |  | Nom de l'objet pédagogique |
|  |  | Description | String |  | Description de l'objet pédagogique |
|  |  | Id_Module | Integer | FK (Modules) | Référence au module lié à l'objet |
| Attributs | Contient les informations des attributs | Id_Attribut | Integer | PK | Identifiant de l'attribut |
|  |  | Numero | Integer |  | Numéro de l'attribut |
|  |  | Valeur | String |  | Valeur de l'attribut |
|  |  | Code_Postal | String |  | Code postal lié à l'attribut |
| Validations | Contient les informations des validations | Id_Validation | Integer | PK | Identifiant de la validation |
|  |  | Libelle | String |  | Nom de la validation |
| Validations_Jsons | Contient les informations des validations JSON | Id_Validation | Integer | PK, FK (Validations) | Référence à la validation |
|  |  | Libelle | String |  | Nom de la validation JSON |
|  |  | Json | Text |  | Données JSON de la validation |
| Tags | Contient les informations des tags | Id_Tag | Integer | PK | Identifiant du tag |
|  |  | Libelle | String |  | Nom du tag |
| Tags_Jsons | Contient les informations des tags JSON | Id_Tag | Integer | PK, FK (Tags) | Référence au tag |
|  |  | Libelle | String |  | Nom du tag JSON |
|  |  | Json | Text |  | Données JSON du tag |
| Etres | Contient les informations des êtres | Id_Etre | Integer | PK | Identifiant de l'être |
|  |  | Libelle | String |  | Nom de l'être |
|  |  | Valeur | String |  | Valeur de l'être |
|  |  | Id_Validation | Integer | FK (Validations) | Référence à la validation |
| Modules | Contient les informations des modules | Id_Module | Integer | PK | Identifiant du module |
|  |  | Libelle | String |  | Nom du module |
|  |  | Description | String |  | Description du module |
| Leçons | Contient les informations des leçons | Id_Lecon | Integer | PK | Identifiant de la leçon |
|  |  | Libelle | String |  | Nom de la leçon |
|  |  | Description | String |  | Description de la leçon |
|  |  | Id_Formation | Integer | FK (Formations) | Référence à la formation liée |
| Remplis | Contient les informations des remplis | Id_Module | Integer | PK, FK (Modules) | Référence au module |
|  |  | Id_Formation | Integer | PK, FK (Formations) | Référence à la formation |
| Utilisateurs_Formations | Table associative pour les utilisateurs et formations | Id_Utilisateur | Integer | PK, FK (Utilisateurs) | Référence à l'utilisateur |
|  |  | Id_Formation | Integer | PK, FK (Formations) | Référence à la formation |
| Utilisateurs_Modules | Table associative pour les utilisateurs et modules | Id_Utilisateur | Integer | PK, FK (Utilisateurs) | Référence à l'utilisateur |
|  |  | Id_Module | Integer | PK, FK (Modules) | Référence au module |
| Utilisateurs_Lecons | Table associative pour les utilisateurs et leçons | Id_Utilisateur | Integer | PK, FK (Utilisateurs) | Référence à l'utilisateur |
|  |  | Id_Lecon | Integer | PK, FK (Leçons) | Référence à la leçon |
| Utilisateurs_Projets | Table associative pour les utilisateurs et projets | Id_Utilisateur | Integer | PK, FK (Utilisateurs) | Référence à l'utilisateur |
|  |  | Id_Projet | Integer | PK, FK (Projets) | Référence au projet |
| Projets | Contient les informations des projets | Id_Projet | Integer | PK | Identifiant du projet |
|  |  | Libelle | String |  | Nom du projet |
|  |  | Description | String |  | Description du projet |
| Projets_Lecons | Table associative pour les projets et leçons | Id_Projet | Integer | PK, FK (Projets) | Référence au projet |
|  |  | Id_Lecon | Integer | PK, FK (Leçons) | Référence à la leçon |
| Projets_Tags | Table associative pour les projets et tags | Id_Projet | Integer | PK, FK (Projets) | Référence au projet |
|  |  | Id_Tag | Integer | PK, FK (Tags) | Référence au tag |


