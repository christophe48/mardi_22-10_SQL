Les bases de données relationnelles sont la base de la majorité des applications. Pour concevoir une BDD relationnelle, SQL est le langage de prédilection.

Avant de coder une BDD, il faut se poser pour établir toutes les tables, les relations entre elles et leurs attributs.

Voici une sélection de commandes classiques en SQL :

Créer une table :
CREATE TABLE `doctors` (
`id` INTEGER PRIMARY KEY AUTOINCREMENT, `name` TEXT,  #autoincrement nous permet d'incrementer automatiquement l'id à chaque entré
`age` INTEGER,
`specialty` TEXT
);
Les commandes suivantes permettront de visualiser plus facilement le contenu de ta table quand tu taperas la commande SELECT * FROM doctors. Saisis-les une fois dans l'interface de SQlite3 :

.mode column
.headers on
La commande suivante permet de lister toutes les tables qui ont déjà été créées dans ton fichier de base de données.

.tables
Une dernière astuce pour afficher simplement toutes les colonnes d'une table donnée. Il faut que tu ais activé le mode .headers on. Ensuite fais :

SELECT * FROM TableName LIMIT 1;
Cela affichera la première ligne du tableau et donc l'ensemble du header au-dessus.

Qu'est-ce que le CRUD ? Ce sont les 4 grandes actions qu'on voudra effectuer sur les entrées d'une BDD :

Create : créer une nouvelle entrée dans une table. Il faut utiliser la commande INSERT ;
Read : lire les entrées d'une table. Il faut utiliser la commande SELECT ;
Update : mettre à jour une entrée d'une table. Il faut utiliser la commande UPDATE ;
Delete : supprimer une entrée. Il faut utiliser la commande DELETE.


Créer une entrée dans une table :
INSERT INTO doctors (name, age, specialty) VALUES ('Dr. Dolladille', 45, 'Dentist');

Lire des éléments (avec ou sans critère de sélection) :
SELECT * FROM doctors;
SELECT * FROM doctors WHERE age = 45;

Mettre à jour une entrée :
UPDATE doctors SET age = 40, name = 'John Smith' WHERE id = 3;

Supprimer une entrée :
DELETE FROM doctors WHERE id= 3;

Lire les éléments d'une table selon un critère d'une table liée :
SELECT * FROM inhabitants
JOIN cities ON cities.id = inhabitants.city_id
WHERE cities.name = 'Paris';
