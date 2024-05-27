# **Script SQL**


DROP TABLE IF EXISTS formation ;
CREATE TABLE formation (idFormation_formation INT(10) AUTO_INCREMENT NOT NULL,
titre_formation VARCHAR(250),
id_user_formation INT,
id_module_formation INT(100),
obj_pedagogique_formation VARCHAR(250),
tags_formation VARCHAR(250),
status_formation VARCHAR(10),
is_valide_formation BOOLEAN,
PRIMARY KEY (idFormation_formation)) ENGINE=InnoDB;

DROP TABLE IF EXISTS module ;
CREATE TABLE module (idModule_module INT(10) AUTO_INCREMENT NOT NULL,
titre_module VARCHAR(250),
id_auteur_module INT,
id_lecon_module BIGINT,
objectifPedagogique VARCHAR(250),
tag VARCHAR(250),
status_module VARCHAR(10),
is_valide_module BOOLEAN,
PRIMARY KEY (idModule_module)) ENGINE=InnoDB;

DROP TABLE IF EXISTS lecon ;
CREATE TABLE lecon (idLecon INT(10) AUTO_INCREMENT NOT NULL,
titre_lecon VARCHAR(250),
id_auteur_lecon INT(10),
obj_pedagogique_lecon VARCHAR(250),
video_lecon VARCHAR(250),
image_lecon VARCHAR(250),
paragraphe_lecon VARCHAR(1000),
tag_lecon VARCHAR(250),
status_lecon VARCHAR(10),
typeContenu VARCHAR(250),
is_valide_lecon BOOLEAN,
PRIMARY KEY (idLecon)) ENGINE=InnoDB;

DROP TABLE IF EXISTS User ;
CREATE TABLE User (idUser_User INT(10) AUTO_INCREMENT NOT NULL,
nom_User VARCHAR(250),
prenom_User VARCHAR(250),
adresse_User VARCHAR(250),
date_naissance_User DATE,
role_User VARCHAR(10),
PRIMARY KEY (idUser_User)) ENGINE=InnoDB;

DROP TABLE IF EXISTS avoir ;
CREATE TABLE avoir (idUser_User **NOT FOUND**(10) AUTO_INCREMENT NOT NULL,
idFormation_formation **NOT FOUND**(10) NOT NULL,
PRIMARY KEY (idUser_User,
idFormation_formation)) ENGINE=InnoDB;

DROP TABLE IF EXISTS contenir ;
CREATE TABLE contenir (idFormation_formation **NOT FOUND**(10) AUTO_INCREMENT NOT NULL,
idModule_module **NOT FOUND**(10) NOT NULL,
PRIMARY KEY (idFormation_formation,
idModule_module)) ENGINE=InnoDB;

DROP TABLE IF EXISTS posseder ;
CREATE TABLE posseder (idModule_module **NOT FOUND**(10) AUTO_INCREMENT NOT NULL,
idLecon INT(10) NOT NULL,
PRIMARY KEY (idModule_module,
idLecon)) ENGINE=InnoDB;

ALTER TABLE avoir ADD CONSTRAINT FK_avoir_idUser_User FOREIGN KEY (idUser_User) REFERENCES User (idUser_User);

ALTER TABLE avoir ADD CONSTRAINT FK_avoir_idFormation_formation FOREIGN KEY (idFormation_formation) REFERENCES formation (idFormation_formation);
ALTER TABLE contenir ADD CONSTRAINT FK_contenir_idFormation_formation FOREIGN KEY (idFormation_formation) REFERENCES formation (idFormation_formation);
ALTER TABLE contenir ADD CONSTRAINT FK_contenir_idModule_module FOREIGN KEY (idModule_module) REFERENCES module (idModule_module);
ALTER TABLE posseder ADD CONSTRAINT FK_posseder_idModule_module FOREIGN KEY (idModule_module) REFERENCES module (idModule_module);
ALTER TABLE posseder ADD CONSTRAINT FK_posseder_idLecon FOREIGN KEY (idLecon) REFERENCES lecon (idLecon);