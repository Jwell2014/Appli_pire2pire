# **Règle de gestion 📄 **

**Visite du site pire2pire.com**

- L’utilisateur peut avoir accès à la page d'accueil de l'application web.
- L’utilisateur peut prendre connaissance des services proposés par pire2pire.
- L’utilisateur  peut s'inscrire et devient alors un user ⇒ apprenant.

**Connexion users**

- Un user possède numéro d’inscription unique, 
- Un user possède un nom,
- Un user possède un prénom, 
- Un user possède une adresse 
- Un user possède une date de naissance
- Un user possède role
- Il existe trois rôles : admin, apprenant et formateur.
- L'admin, l’apprenant ou le formateur peut se connecter via un formulaire de connexion.
    - L'admin, l’apprenant ou le formateur devra renseigner son email et son mot de passe afin de s'authentifier.
- Le role admin possède tous les accès et méthodes de l’application
- Le role admin crée les accès pour les formateurs
- Le role formateur peut accéder aux CRUD des formation, des modules et des leçons
- Le role apprenant peut accéder aux contenu des formations, des modules et des leçons

**Suppression de compte**

- Un admin peut supprimer un formateur ou un apprenant de la plateforme.
- Un formateur peut supprimer son compte personnel de la plateforme.
- Un apprenant peut supprimer son compte personnel de la plateforme.

**Gestion des leçons**

- Une leçon possède un titre
- Une leçon possède un auteur (formateur)
- Une leçon possède un objectif pédagogique
- Une leçon possède une ou plusieurs vidéos
- Une leçon possède une ou plusieurs images
- Une leçon possède une ou plusieurs images
- Une leçon possède un ou plusieurs paragraphes
- Une leçon possède un ou plusieurs tags.
- Une leçon possède un status(Draft,Active,Archive)
- Une leçon possède IsValide
- Une leçon doit contenir une ou plusieurs videos.
- Une leçon doit contenir une ou plusieurs images.
- Une leçon doit contenir un ou plusieurs paragraphes.
- Une leçon peut avoir le status : Draft/Active/archive.
- Si elle a le status archive elle ne pourra plus etre suivi par un apprenant ou utiliser dans une formation ou module
- Si elle a le status draft elle ne sera visible que par le professeur qui l’as crée
- Si elle a le status active elle sera visible pour tous les users
- Une leçon peut être rattachée à aucun ou plusieurs modules.
- Une leçon peut etre valider par 0 ou plusieurs apprenants
- Si une leçon est supprimé, alors cette dernière disparaitra du ou des modules et formations auxquels elle est rattachée.
- Le formateur peut créer une ou plusieurs leçons.
- Le formateur peut modifier les leçons qu'il a créées.
- Le formateur peut supprimer les leçons qu'il a créées.
- Si un formateur supprimer une leçon celle ci ne sera plus accessible aux apprenants qui y sont rattachés et retirer du ou des modules qui l’utilise.
- un apprenant peut suivre une ou plusieurs leçons
- un apprenant peut valider ou non une ou plusieurs leçons

**Gestion des modules**

- Le module possède un titre
- Le module possède un auteur (formateur)
- Le module possède une ou plusieurs leçon
- Le module possède un objectif pédagogique
- Le module possède un ou plusieurs tags.
- Le module possède status
- Le module possède IsValide
- Le module doit contenir une ou plusieurs leçons.
- Le module peut avoir le status : Draft/Active/archive.
- Le modules peut être rattaché à aucune ou plusieurs formations.
- Si un module est supprimé, cela n'entraine pas la suppression de la ou des leçons qui étaient rattachées à ce dernier.
- Si un module est supprimé dans une formation, alors ce dernier disparaitra de la formation actuelle mais pas des formations auxquelles il est rattaché.
- Le formateur peut créer un ou plusieurs modules.
- Le formateur peut modifier les modules qu'il a créés.
- Le formateur peut supprimer les modules qu'il a créés.
- un apprenant peut suivre a un ou plusieurs modules
- Si toutes les leçons d’un module sont “Valide” alors le module est validé.
- un apprenant peut valider ou non un ou plusieurs modules.
- Un module peut etre valider par 0 ou plusieurs apprenants.
- Un module est considéré comme terminé lorsque que tous les leçons qui le compose sont validé.

**Gestion des formations**

- Une formation possède un titre
- Une formation possède un ou des auteurs (formateur)
- Une formation possède un ou des auteurs (formateur)
- Une formation possède un ou plusieurs modules
- Une formation possède un objectif pédagogique
- Une formation possède un ou plusieurs tags.
- Une formation possède status(Draft,Active,Archive)
- Une formation possède IsValide
- La formation peut être créer par un ou plusieurs formateurs
- La formation peut être modifier par le ou les formateurs qui ont accès
- La formation peut être supprimer par le ou les formateurs qui ont accès
- Si une formation est supprimer on passe son status en draft
- La formation peut etre suivie par 0 ou plusieurs apprenants
- La formation doit contenir un ou plusieurs modules
- La formation est considé comme terminer lorsque que tous les modules qui l’as compose sont validé.

**Gestion des formations par les formateurs**

- Le formateur peut créer une ou plusieurs formations.
- Le formateur peut modifier les formations qu'il a créées.
- Le formateur peut supprimer les formations qu'il a créées.
- Si une formation est supprimée, alors les apprenants inscrits à cette formation n'y auront plus accès.
- Si une formation est supprimée, cela n'entraine pas la suppression du ou des modules qui étaient rattachés à cette dernière.

**Gestion des formations par les apprenants**

- Un apprenant peut s'inscrire à une ou plusieurs formations.
- Un apprenant peut quitter une ou plusieurs formations
- Un apprenant peut supprimer une formation de sa liste de formation
- Si un apprenant supprime une formation cela remet toutes les leçons de celle-ci comme “KO”
- Un apprenant peut valider manuellement, s'il le souhaite, certains modules présents dans une formation qu'il maîtrise déjà.
- Une formation est considérée comme terminée lorsque tous les modules ont été validés.