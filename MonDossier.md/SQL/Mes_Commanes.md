Mes commandes :



Effectuez une requête qui permettra d'obtenir le titre et l'auteur de tous les livres présents dans la table LIVRES. : 


SELECT titre, auteur
FROM LIVRES


Pour trouver les livres (seulment les livres !!) d'un auteur définie on ajoute WHERE auteur='nom_de_l'auteur'

SELECT titre
FROM LIVRES
WHERE auteur='Asimov'



Cette requête permet d'obtenir les titres des livres publiés après 1945 qui ont une note supérieure ou égale à 9 :


SELECT titre, ann_publi
FROM LIVRES
WHERE note>=9 AND ann_publi>1945


Cette requête SQL permet d'obtenir les livres de K.Dick classés du plus ancien ou plus récent.

SELECT titre, ann_publi
FROM LIVRES
WHERE auteur='K.Dick' ORDER BY ann_publi



Cette commande permet d'ajouter des auteurs dans une table

INSERT INTO AUTEURS 
(id,nom,prenom,ann_naissance,langue_ecriture)   <-- les attributs des auteurs 
VALUES                                          <-- a partir de la on peut données les attributs des auteurs 
(1,'Orwell','George',1903,'anglais'),

Cette commande permet d'avoir tout les livres écrit apres 1945 en réunissant deux tables

SELECT titre,nom, prenom
FROM LIVRES
INNER JOIN AUTEURS ON LIVRES.id_auteur = AUTEURS.id AND ann_publi>1945




Cette requête SQL, ajoute à la table LIVRES le livre suivant :          id : 17
                                                                        titre : "2001 : L'Odyssée de l'espace"
                                                                        auteur : "Clarcke"
                                                                        année de publication : 1968
                                                                        note : 7

INSERT INTO LIVRES
(id,titre,auteur,ann_publi,note)
VALUES
(17,'2001 : L"Odyssée de l"espace','Clarcke',1968,7);


Cette commande permet de mettre a jour les notes a 10 des livre écrit apres 1945 de l'auteur Asimov 

UPDATE LIVRES
SET note=10
WHERE auteur='Asimov' AND ann_publi>1945



Pour supprimer les livres écrit avant 1945 

DELETE FROM LIVRES
WHERE ann_publi<1945