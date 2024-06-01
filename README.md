# azuresqltuto
Vous trouverez ici les instructions afin de déployer une base de données relationnelle reposant sur Azure SQL Database

Afin de préparer l'environnement, veuillez d'abord télécharger Azure Data Studio en accédant à cette page web--> https://learn.microsoft.com/en-us/azure-data-studio/download-azure-data-studio?tabs=win-install%2Cwin-user-install%2Credhat-install%2Cwindows-uninstall%2Credhat-uninstall
En fonction de votre système d'exploitation (Windows, Mac, ou Linux) téléchargez la version de votre choix et exécutez le fichier d'installation.


Une fois Azure Data Studio installé, ouvrez l'application et téléchargez SQL Server Import afin d'importer le fichier csv et créer une table à partir de ce fichier.

Requêtes:

Clients Achats >5

SELECT * FROM db_owner.dataeco WHERE quantity_ordered > 5



Avoir les ventes pour la marque Samsung 

SELECT * FROM db_owner.dataeco WHERE mobile_brand = 'samsung'



Total des produits vendus

SELECT SUM(quantity_ordered) AS totalsales FROM db_owner.dataeco


Chiffre d’affaire par client

SELECT *,
  unit_price * quantity_ordered AS chiffre_affaires
FROM db_owner.dataeco;

Savoir combine de google pixel ont été vendus


SELECT SUM(quantity_ordered) 
as ca_google_pixel
FROM db_owner.dataeco
WHERE mobile_device = 'google pixel'
