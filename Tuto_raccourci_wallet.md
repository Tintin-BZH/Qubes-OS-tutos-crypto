# Tutoriel : Créer des raccourci vers vos wallets dans Qubes OS

Objectif du tuto : créer des raccourcis pour faciliter le lancement de vos wallets, directement accessibles dans votre menu Qubes OS :

![Qubes_Raccourcis00](/IMG/Qubes-raccourcis00.jpg)

Pré-requis :
- Avoir installé un wallet fonctionnel dans un Qube
- Connaître la commande nécessaire à son éxécution

## 1) Télécharger un logo pour votre raccourci

(optionnel mais c'est plus joli :) )
A faire depuis le Firefox du Qube contenant votre wallet. Inutile de prendre une image trop grande. Téléchargez-la sur un site de confiance (coinmarketcap, coingecko, le site du coin...)
Enregistrez-la à un endroit connu.

## 2) Copier un raccourci .desktop existant du template

Dans le Qube contenant votre wallet, ouvrez l'explorateur de fichiers Thunar et allez dans le dossier /usr/share/applications. Il contient toutes les applications de votre template. Copiez l'un d'entre eux ayant l'extension .desktop

![Qubes_Raccourcis03](/IMG/Qubes-raccourcis03.jpg)

## 3) le coller dans les raccourcis locaux de votre Qube

Allez ensuite dans /home/user/.local/share/applications pour coller le raccourci copié

Notes :
- .local est un dossier caché. Pour s'y rendre, faites Ctrl+H pour afficher les dossiers cachés, ou tapez le chemin dans la barre d'adresse du gestionnaire de fichiers.
- Si le dossier applications n'existe pas dans /home/user/.local/share , créez-le (applications, en minuscules)

## 4) Mettre à jour le raccourci puis test

Renommez d'abord votre raccourci en "nomduwallet.desktop".
Ensuite faites un cloc droit sur votre raccourci > Edit launcher puis changez les valeurs :

![Qubes_Raccourcis04](/IMG/Qubes-raccourcis04.jpg)

- Name : Le nom tel qu'il apparaîtra dans le menu
- Comment : Description, pas utile
- Command : la commande qui sert à lancer le wallet.
- Working directory : Le dossier dans lequel se trouve l'exécutable du wallet
- Icon : Le logo du wallet, choisissez "fichiers images" puis choisissez votre logo téléchargez

Enregistrez une fois tout mis à jour, puis double-cliquez sur le raccourci .desktop pour voir si votre wallet se lance.

## 5) Ajouter à votre menu.

Dans les paramètres de votre Qube, allez à l'onglet "applications", faites "Refresh Applications". Votre wallet devrait arriver dans la liste de gauche. Déplacez-le dans la liste de droite puis appliquez

![Qubes_Raccourcis05](/IMG/Qubes-raccourcis05.jpg)

Et c'est finiLe wallet sera dans votre menu normalement. Un clic droit dessus permet aussi de l'épingler en favori dans le menu.

![Qubes_Raccourcis01](/IMG/Qubes-raccourcis01.jpg)


