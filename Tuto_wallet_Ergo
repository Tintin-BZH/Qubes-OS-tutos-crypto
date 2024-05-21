# Tuto installation du wallet Ergo dans Qubes OS

Objectif du tuto : installer un wallet Ergo sur Qubes OS

![Qubes_Dynex](/IMG/Qubes-dynex01.jpg)

## 1) Création du Qube :

Pour cela, créez votre Qube (VM) pour votre wallet Ergo (conseil : clonez le Qube "untrusted" si vous ne l'avez pasutilisé), et choisissez lui le template Fedora (par défaut).

## 2) Installation des dépendances dans le template :

Dans votre template Fedora, installez wine avec cette commande dans un terminal :
`sudo dnf install java-latest-openjdk.x86_64`

## 3) Téléchargement du wallet :

Vous aurez besoin de Firefox pour télécharger le wallet, du gestionnaire du fichier Thunar et/ou du terminal pour extraire, le rendre exécutable et le lancer.

Téléchargez le wallet Ergo sur le Github : hhttps://github.com/ergoplatform/ergo-wallet-app/releases

Vous allez donc prendre le wallet GUI terminant par **linux-x64.jar**

## 4) Lancement du wallet :

L'exécutable doit d'abord être autorisé comme exécutable. Pour cela, clic droit dessus > properties > onglet permissions > Cocher "allow this file to run as a program
Note : Possible aussi avec la commande `chmod +x lefichier`

Puis pour le lancer, clic droit dessus > open with other applications > use a custom command. Et saisir ``java -jar` (cocher "use as default" et valider). Normalement il se lance !

## 5) Commande pour le lancer (utile pour créer un raccourci) :

`java -jar ergo-wallet-app-xxxxxxx.jar` (mettre le bon nom de fichier)
