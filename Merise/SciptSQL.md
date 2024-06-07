# **Script SQL**


#------------------------------------------------------------
#        Script MySQL.
#------------------------------------------------------------


#------------------------------------------------------------
# Table: Roles
#------------------------------------------------------------

CREATE TABLE Roles(
        id_role Int  Auto_increment  NOT NULL ,
        type    Varchar (50)
	,CONSTRAINT Roles_PK PRIMARY KEY (id_role)
)ENGINE=InnoDB;


#------------------------------------------------------------
# Table: Adresses
#------------------------------------------------------------

CREATE TABLE Adresses(
        id_adresse  Int  Auto_increment  NOT NULL ,
        numero      Int NOT NULL ,
        rue         Varchar (50) NOT NULL ,
        ville       Varchar (50) NOT NULL ,
        code_postal Varchar (50) NOT NULL ,
        pays        Varchar (50) NOT NULL
	,CONSTRAINT Adresses_PK PRIMARY KEY (id_adresse)
)ENGINE=InnoDB;


#------------------------------------------------------------
# Table: Utilisateurs
#------------------------------------------------------------

CREATE TABLE Utilisateurs(
        id_utilisateur    Int  Auto_increment  NOT NULL ,
        nom               Varchar (50) ,
        prenom            Varchar (50) ,
        email             Varchar (50) ,
        mdp               Varchar (50) ,
        date_de_naissance Date ,
        id_adresse        Int NOT NULL
	,CONSTRAINT Utilisateurs_PK PRIMARY KEY (id_utilisateur)
)ENGINE=InnoDB;


#------------------------------------------------------------
# Table: Paragraphes
#------------------------------------------------------------

CREATE TABLE Paragraphes(
        id      Int  Auto_increment  NOT NULL ,
        nom     Varchar (50) NOT NULL ,
        contenu Text NOT NULL
	,CONSTRAINT Paragraphes_PK PRIMARY KEY (id)
)ENGINE=InnoDB;


#------------------------------------------------------------
# Table: Videos
#------------------------------------------------------------

CREATE TABLE Videos(
        id_video Int  Auto_increment  NOT NULL ,
        nom      Varchar (50) NOT NULL ,
        url      Varchar (50) NOT NULL
	,CONSTRAINT Videos_PK PRIMARY KEY (id_video)
)ENGINE=InnoDB;


#------------------------------------------------------------
# Table: Images
#------------------------------------------------------------

CREATE TABLE Images(
        id  Int  Auto_increment  NOT NULL ,
        nom Varchar (50) NOT NULL ,
        url Varchar (50) NOT NULL
	,CONSTRAINT Images_PK PRIMARY KEY (id)
)ENGINE=InnoDB;


#------------------------------------------------------------
# Table: Status
#------------------------------------------------------------

CREATE TABLE Status(
        id  Int  Auto_increment  NOT NULL ,
        nom Varchar (50) NOT NULL
	,CONSTRAINT Status_PK PRIMARY KEY (id)
)ENGINE=InnoDB;


#------------------------------------------------------------
# Table: Formations
#------------------------------------------------------------

CREATE TABLE Formations(
        id        Int  Auto_increment  NOT NULL ,
        titre     Varchar (50) ,
        valider   Bool NOT NULL ,
        id_Status Int NOT NULL
	,CONSTRAINT Formations_PK PRIMARY KEY (id)
)ENGINE=InnoDB;


#------------------------------------------------------------
# Table: Modules
#------------------------------------------------------------

CREATE TABLE Modules(
        id_module Int  Auto_increment  NOT NULL ,
        titre     Varchar (50) ,
        valider   Bool NOT NULL ,
        id        Int NOT NULL
	,CONSTRAINT Modules_PK PRIMARY KEY (id_module)
)ENGINE=InnoDB;


#------------------------------------------------------------
# Table: Tag
#------------------------------------------------------------

CREATE TABLE Tag(
        id  Int  Auto_increment  NOT NULL ,
        nom Varchar (50) NOT NULL
	,CONSTRAINT Tag_PK PRIMARY KEY (id)
)ENGINE=InnoDB;


#------------------------------------------------------------
# Table: Validation_leçons
#------------------------------------------------------------

CREATE TABLE Validation_lecons(
        id_validation_lecon Int  Auto_increment  NOT NULL ,
        id_lecon            Int ,
        id_utilisateur      Int
	,CONSTRAINT Validation_lecons_AK UNIQUE (id_lecon,id_utilisateur)
	,CONSTRAINT Validation_lecons_PK PRIMARY KEY (id_validation_lecon)
)ENGINE=InnoDB;


#------------------------------------------------------------
# Table: Attribuer
#------------------------------------------------------------

CREATE TABLE Attribuer(
        id_role        Int NOT NULL ,
        id_utilisateur Int NOT NULL
	,CONSTRAINT Attribuer_PK PRIMARY KEY (id_role,id_utilisateur)
)ENGINE=InnoDB;


#------------------------------------------------------------
# Table: Valider
#------------------------------------------------------------

CREATE TABLE Valider(
        id_validation_lecon Int NOT NULL ,
        id_utilisateur      Int NOT NULL
	,CONSTRAINT Valider_PK PRIMARY KEY (id_validation_lecon,id_utilisateur)
)ENGINE=InnoDB;


#------------------------------------------------------------
# Table: Lier_module
#------------------------------------------------------------

CREATE TABLE Lier_module(
        id_module Int NOT NULL ,
        id        Int NOT NULL
	,CONSTRAINT Lier_module_PK PRIMARY KEY (id_module,id)
)ENGINE=InnoDB;


#------------------------------------------------------------
# Table: Lier_formation
#------------------------------------------------------------

CREATE TABLE Lier_formation(
        id     Int NOT NULL ,
        id_Tag Int NOT NULL
	,CONSTRAINT Lier_formation_PK PRIMARY KEY (id,id_Tag)
)ENGINE=InnoDB;


#------------------------------------------------------------
# Table: Ecrire_formation
#------------------------------------------------------------

CREATE TABLE Ecrire_formation(
        id            Int NOT NULL ,
        id_Formations Int NOT NULL
	,CONSTRAINT Ecrire_formation_PK PRIMARY KEY (id,id_Formations)
)ENGINE=InnoDB;


#------------------------------------------------------------
# Table: Ecrire_module
#------------------------------------------------------------

CREATE TABLE Ecrire_module(
        id        Int NOT NULL ,
        id_module Int NOT NULL
	,CONSTRAINT Ecrire_module_PK PRIMARY KEY (id,id_module)
)ENGINE=InnoDB;


#------------------------------------------------------------
# Table: Imager_formation
#------------------------------------------------------------

CREATE TABLE Imager_formation(
        id            Int NOT NULL ,
        id_Formations Int NOT NULL
	,CONSTRAINT Imager_formation_PK PRIMARY KEY (id,id_Formations)
)ENGINE=InnoDB;


#------------------------------------------------------------
# Table: Imager_module
#------------------------------------------------------------

CREATE TABLE Imager_module(
        id        Int NOT NULL ,
        id_module Int NOT NULL
	,CONSTRAINT Imager_module_PK PRIMARY KEY (id,id_module)
)ENGINE=InnoDB;


#------------------------------------------------------------
# Table: Projeter_formation
#------------------------------------------------------------

CREATE TABLE Projeter_formation(
        id_video Int NOT NULL ,
        id       Int NOT NULL
	,CONSTRAINT Projeter_formation_PK PRIMARY KEY (id_video,id)
)ENGINE=InnoDB;


#------------------------------------------------------------
# Table: Projeter_module
#------------------------------------------------------------

CREATE TABLE Projeter_module(
        id_video  Int NOT NULL ,
        id_module Int NOT NULL
	,CONSTRAINT Projeter_module_PK PRIMARY KEY (id_video,id_module)
)ENGINE=InnoDB;


#------------------------------------------------------------
# Table: Contenir
#------------------------------------------------------------

CREATE TABLE Contenir(
        id        Int NOT NULL ,
        id_module Int NOT NULL
	,CONSTRAINT Contenir_PK PRIMARY KEY (id,id_module)
)ENGINE=InnoDB;


#------------------------------------------------------------
# Table: Créer_module
#------------------------------------------------------------

CREATE TABLE Creer_module(
        id_module      Int NOT NULL ,
        id_utilisateur Int NOT NULL
	,CONSTRAINT Creer_module_PK PRIMARY KEY (id_module,id_utilisateur)
)ENGINE=InnoDB;


#------------------------------------------------------------
# Table: Créer_formation
#------------------------------------------------------------

CREATE TABLE Creer_formation(
        id             Int NOT NULL ,
        id_utilisateur Int NOT NULL
	,CONSTRAINT Creer_formation_PK PRIMARY KEY (id,id_utilisateur)
)ENGINE=InnoDB;


#------------------------------------------------------------
# Table: Leçons
#------------------------------------------------------------

CREATE TABLE Lecons(
        id_lecon     Int  Auto_increment  NOT NULL ,
        titre        Varchar (50) ,
        id           Int NOT NULL ,
        id_objPedago Int
	,CONSTRAINT Lecons_PK PRIMARY KEY (id_lecon)
)ENGINE=InnoDB;


#------------------------------------------------------------
# Table: ObjPedagogiques
#------------------------------------------------------------

CREATE TABLE ObjPedagogiques(
        id_objPedago Int  Auto_increment  NOT NULL ,
        nom          Varchar (50) NOT NULL ,
        contenu      Text NOT NULL ,
        id_lecon     Int ,
        id_module    Int NOT NULL ,
        id           Int NOT NULL
	,CONSTRAINT ObjPedagogiques_PK PRIMARY KEY (id_objPedago)
)ENGINE=InnoDB;


#------------------------------------------------------------
# Table: Etre
#------------------------------------------------------------

CREATE TABLE Etre(
        id_lecon            Int NOT NULL ,
        id_validation_lecon Int NOT NULL
	,CONSTRAINT Etre_PK PRIMARY KEY (id_lecon,id_validation_lecon)
)ENGINE=InnoDB;


#------------------------------------------------------------
# Table: Lier_leçon
#------------------------------------------------------------

CREATE TABLE Lier_lecon(
        id_lecon Int NOT NULL ,
        id       Int NOT NULL
	,CONSTRAINT Lier_lecon_PK PRIMARY KEY (id_lecon,id)
)ENGINE=InnoDB;


#------------------------------------------------------------
# Table: Ecrire_leçon
#------------------------------------------------------------

CREATE TABLE Ecrire_lecon(
        id       Int NOT NULL ,
        id_lecon Int NOT NULL
	,CONSTRAINT Ecrire_lecon_PK PRIMARY KEY (id,id_lecon)
)ENGINE=InnoDB;


#------------------------------------------------------------
# Table: Imager_leçon
#------------------------------------------------------------

CREATE TABLE Imager_lecon(
        id       Int NOT NULL ,
        id_lecon Int NOT NULL
	,CONSTRAINT Imager_lecon_PK PRIMARY KEY (id,id_lecon)
)ENGINE=InnoDB;


#------------------------------------------------------------
# Table: Projeter_leçon
#------------------------------------------------------------

CREATE TABLE Projeter_lecon(
        id_video Int NOT NULL ,
        id_lecon Int NOT NULL
	,CONSTRAINT Projeter_lecon_PK PRIMARY KEY (id_video,id_lecon)
)ENGINE=InnoDB;


#------------------------------------------------------------
# Table: Remplir
#------------------------------------------------------------

CREATE TABLE Remplir(
        id_module Int NOT NULL ,
        id_lecon  Int NOT NULL
	,CONSTRAINT Remplir_PK PRIMARY KEY (id_module,id_lecon)
)ENGINE=InnoDB;


#------------------------------------------------------------
# Table: Créer_leçon
#------------------------------------------------------------

CREATE TABLE Creer_lecon(
        id_lecon       Int NOT NULL ,
        id_utilisateur Int NOT NULL
	,CONSTRAINT Creer_lecon_PK PRIMARY KEY (id_lecon,id_utilisateur)
)ENGINE=InnoDB;




ALTER TABLE Utilisateurs
	ADD CONSTRAINT Utilisateurs_Adresses0_FK
	FOREIGN KEY (id_adresse)
	REFERENCES Adresses(id_adresse);

ALTER TABLE Formations
	ADD CONSTRAINT Formations_Status0_FK
	FOREIGN KEY (id_Status)
	REFERENCES Status(id);

ALTER TABLE Modules
	ADD CONSTRAINT Modules_Status0_FK
	FOREIGN KEY (id)
	REFERENCES Status(id);

ALTER TABLE Attribuer
	ADD CONSTRAINT Attribuer_Roles0_FK
	FOREIGN KEY (id_role)
	REFERENCES Roles(id_role);

ALTER TABLE Attribuer
	ADD CONSTRAINT Attribuer_Utilisateurs1_FK
	FOREIGN KEY (id_utilisateur)
	REFERENCES Utilisateurs(id_utilisateur);

ALTER TABLE Valider
	ADD CONSTRAINT Valider_Validation_lecons0_FK
	FOREIGN KEY (id_validation_lecon)
	REFERENCES Validation_lecons(id_validation_lecon);

ALTER TABLE Valider
	ADD CONSTRAINT Valider_Utilisateurs1_FK
	FOREIGN KEY (id_utilisateur)
	REFERENCES Utilisateurs(id_utilisateur);

ALTER TABLE Lier_module
	ADD CONSTRAINT Lier_module_Modules0_FK
	FOREIGN KEY (id_module)
	REFERENCES Modules(id_module);

ALTER TABLE Lier_module
	ADD CONSTRAINT Lier_module_Tag1_FK
	FOREIGN KEY (id)
	REFERENCES Tag(id);

ALTER TABLE Lier_formation
	ADD CONSTRAINT Lier_formation_Formations0_FK
	FOREIGN KEY (id)
	REFERENCES Formations(id);

ALTER TABLE Lier_formation
	ADD CONSTRAINT Lier_formation_Tag1_FK
	FOREIGN KEY (id_Tag)
	REFERENCES Tag(id);

ALTER TABLE Ecrire_formation
	ADD CONSTRAINT Ecrire_formation_Paragraphes0_FK
	FOREIGN KEY (id)
	REFERENCES Paragraphes(id);

ALTER TABLE Ecrire_formation
	ADD CONSTRAINT Ecrire_formation_Formations1_FK
	FOREIGN KEY (id_Formations)
	REFERENCES Formations(id);

ALTER TABLE Ecrire_module
	ADD CONSTRAINT Ecrire_module_Paragraphes0_FK
	FOREIGN KEY (id)
	REFERENCES Paragraphes(id);

ALTER TABLE Ecrire_module
	ADD CONSTRAINT Ecrire_module_Modules1_FK
	FOREIGN KEY (id_module)
	REFERENCES Modules(id_module);

ALTER TABLE Imager_formation
	ADD CONSTRAINT Imager_formation_Images0_FK
	FOREIGN KEY (id)
	REFERENCES Images(id);

ALTER TABLE Imager_formation
	ADD CONSTRAINT Imager_formation_Formations1_FK
	FOREIGN KEY (id_Formations)
	REFERENCES Formations(id);

ALTER TABLE Imager_module
	ADD CONSTRAINT Imager_module_Images0_FK
	FOREIGN KEY (id)
	REFERENCES Images(id);

ALTER TABLE Imager_module
	ADD CONSTRAINT Imager_module_Modules1_FK
	FOREIGN KEY (id_module)
	REFERENCES Modules(id_module);

ALTER TABLE Projeter_formation
	ADD CONSTRAINT Projeter_formation_Videos0_FK
	FOREIGN KEY (id_video)
	REFERENCES Videos(id_video);

ALTER TABLE Projeter_formation
	ADD CONSTRAINT Projeter_formation_Formations1_FK
	FOREIGN KEY (id)
	REFERENCES Formations(id);

ALTER TABLE Projeter_module
	ADD CONSTRAINT Projeter_module_Videos0_FK
	FOREIGN KEY (id_video)
	REFERENCES Videos(id_video);

ALTER TABLE Projeter_module
	ADD CONSTRAINT Projeter_module_Modules1_FK
	FOREIGN KEY (id_module)
	REFERENCES Modules(id_module);

ALTER TABLE Contenir
	ADD CONSTRAINT Contenir_Formations0_FK
	FOREIGN KEY (id)
	REFERENCES Formations(id);

ALTER TABLE Contenir
	ADD CONSTRAINT Contenir_Modules1_FK
	FOREIGN KEY (id_module)
	REFERENCES Modules(id_module);

ALTER TABLE Creer_module
	ADD CONSTRAINT Creer_module_Modules0_FK
	FOREIGN KEY (id_module)
	REFERENCES Modules(id_module);

ALTER TABLE Creer_module
	ADD CONSTRAINT Creer_module_Utilisateurs1_FK
	FOREIGN KEY (id_utilisateur)
	REFERENCES Utilisateurs(id_utilisateur);

ALTER TABLE Creer_formation
	ADD CONSTRAINT Creer_formation_Formations0_FK
	FOREIGN KEY (id)
	REFERENCES Formations(id);

ALTER TABLE Creer_formation
	ADD CONSTRAINT Creer_formation_Utilisateurs1_FK
	FOREIGN KEY (id_utilisateur)
	REFERENCES Utilisateurs(id_utilisateur);

ALTER TABLE Lecons
	ADD CONSTRAINT Lecons_Status0_FK
	FOREIGN KEY (id)
	REFERENCES Status(id);

ALTER TABLE Lecons
	ADD CONSTRAINT Lecons_ObjPedagogiques1_FK
	FOREIGN KEY (id_objPedago)
	REFERENCES ObjPedagogiques(id_objPedago);

ALTER TABLE Lecons 
	ADD CONSTRAINT Lecons_ObjPedagogiques0_AK 
	UNIQUE (id_objPedago);

ALTER TABLE ObjPedagogiques
	ADD CONSTRAINT ObjPedagogiques_Lecons0_FK
	FOREIGN KEY (id_lecon)
	REFERENCES Lecons(id_lecon);

ALTER TABLE ObjPedagogiques
	ADD CONSTRAINT ObjPedagogiques_Modules1_FK
	FOREIGN KEY (id_module)
	REFERENCES Modules(id_module);

ALTER TABLE ObjPedagogiques
	ADD CONSTRAINT ObjPedagogiques_Formations2_FK
	FOREIGN KEY (id)
	REFERENCES Formations(id);

ALTER TABLE ObjPedagogiques 
	ADD CONSTRAINT ObjPedagogiques_Lecons0_AK 
	UNIQUE (id_lecon);

ALTER TABLE Etre
	ADD CONSTRAINT Etre_Lecons0_FK
	FOREIGN KEY (id_lecon)
	REFERENCES Lecons(id_lecon);

ALTER TABLE Etre
	ADD CONSTRAINT Etre_Validation_lecons1_FK
	FOREIGN KEY (id_validation_lecon)
	REFERENCES Validation_lecons(id_validation_lecon);

ALTER TABLE Lier_lecon
	ADD CONSTRAINT Lier_lecon_Lecons0_FK
	FOREIGN KEY (id_lecon)
	REFERENCES Lecons(id_lecon);

ALTER TABLE Lier_lecon
	ADD CONSTRAINT Lier_lecon_Tag1_FK
	FOREIGN KEY (id)
	REFERENCES Tag(id);

ALTER TABLE Ecrire_lecon
	ADD CONSTRAINT Ecrire_lecon_Paragraphes0_FK
	FOREIGN KEY (id)
	REFERENCES Paragraphes(id);

ALTER TABLE Ecrire_lecon
	ADD CONSTRAINT Ecrire_lecon_Lecons1_FK
	FOREIGN KEY (id_lecon)
	REFERENCES Lecons(id_lecon);

ALTER TABLE Imager_lecon
	ADD CONSTRAINT Imager_lecon_Images0_FK
	FOREIGN KEY (id)
	REFERENCES Images(id);

ALTER TABLE Imager_lecon
	ADD CONSTRAINT Imager_lecon_Lecons1_FK
	FOREIGN KEY (id_lecon)
	REFERENCES Lecons(id_lecon);

ALTER TABLE Projeter_lecon
	ADD CONSTRAINT Projeter_lecon_Videos0_FK
	FOREIGN KEY (id_video)
	REFERENCES Videos(id_video);

ALTER TABLE Projeter_lecon
	ADD CONSTRAINT Projeter_lecon_Lecons1_FK
	FOREIGN KEY (id_lecon)
	REFERENCES Lecons(id_lecon);

ALTER TABLE Remplir
	ADD CONSTRAINT Remplir_Modules0_FK
	FOREIGN KEY (id_module)
	REFERENCES Modules(id_module);

ALTER TABLE Remplir
	ADD CONSTRAINT Remplir_Lecons1_FK
	FOREIGN KEY (id_lecon)
	REFERENCES Lecons(id_lecon);

ALTER TABLE Creer_lecon
	ADD CONSTRAINT Creer_lecon_Lecons0_FK
	FOREIGN KEY (id_lecon)
	REFERENCES Lecons(id_lecon);

ALTER TABLE Creer_lecon
	ADD CONSTRAINT Creer_lecon_Utilisateurs1_FK
	FOREIGN KEY (id_utilisateur)
	REFERENCES Utilisateurs(id_utilisateur);
