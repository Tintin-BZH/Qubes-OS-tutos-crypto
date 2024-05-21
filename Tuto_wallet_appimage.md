# Tuto installation d'un wallet au format .Appimage dans Qubes OS

Objectif du tuto : tout est dans le titre :P Exemples de wallets dans ce format : Alephium, Radiant, Zelcore...

## 1) Création du Qube :

Pour cela, créez votre Qube (VM) pour votre futur wallet (conseil : clonez le Qube "untrusted" si vous ne l'avez pasutilisé), et choisissez lui le template Fedora (par défaut).

## 2) Installation des dépendances dans le template :

Dans votre template Fedora, installez wine avec cette commande dans un terminal :
`sudo dnf install fuse fuse-libs`

## 3) Téléchargement du wallet :

Vous aurez besoin de Firefox pour télécharger le wallet, du gestionnaire du fichier Thunar et/ou du terminal pour extraire, le rendre exécutable et le lancer.

Téléchargez votre wallet au format .appimage

## 4) Lancement du wallet :

L'exécutable doit d'abord être autorisé comme exécutable. Pour cela, clic droit dessus > properties > onglet permissions > Cocher "allow this file to run as a program
Note : Possible aussi avec la commande `chmod +x lefichier.appimage`

Puis ormalement il se lance au double-clic !

## 5) Commande pour le lancer (utile pour créer un raccourci) :

`./lefichier.appimage` (mettre le bon nom de fichier)
