# Tuto installation du wallet Dynex dans Qubes OS

Objectif du tuto : installer un wallet Dynex sur Qubes OS

![Qubes_Dynex](/IMG/Qubes-dynexO1.jpg)

## 1) Version pour Windows via Wine (fonctionne quelque-soit votre CPU)

Oui, une version Windows sous Qubes OS, parfaitement :P
La raison : le wallet pour Linux (Ubuntu) ne se lance pas sur certains processeurs anciens. L'alternative est d'y installer la version Windows du Wallet grâce au logiciel Wine.

### 1.1) Création du Qube :

Pour cela, créez votre Qube (VM) pour votre wallet Dynex (conseil : clonez le Qube "untrusted" si vous ne l'avez pasutilisé), et choisissez lui le template Fedora (par défaut).

### 1.2) Installation des dépendances dans le template :

Dans votre template Fedora, installez wine avec cette commande dans un terminal :
`sudo dnf install wine`

### 1.3) Installation du wallet :

Vous aurez besoin de Firefox pour télécharger le wallet, du gestionnaire du fichier Thunar et/ou du terminal pour extraire, le rendre exécutable et le lancer.

Téléchargez le wallet Dynex sur le Github : https://github.com/dynexcoin/Dynex/releases

Vous allez donc prendre le wallet GUI pour Windows :  Dynex-main-8e9f077-windows-WalletGUI.zip

Téléchargez-le et dézippez-le. Vous y trouverez **dynexwallet.exe**, faites un clic droit dessus > Ouvrir avec > Wine (disponible si vous l'avez bien installé dans votre template)

Vous pouvez mettre ce choix par défaut pour qu'il s'ouvre au double clic laprochaine fois ;)

Commande pour le lancer (utile pour créer un raccourci) : `wine dynexwallet.exe`

## 2) Version pour Ubuntu (plus "propre" mais ne fonctionne pas sur certains anciens processeurs)

Alors ma méthode n'est probablement pas la seule solution, mais elle marche :
Le wallet Dynex indiqué comme compatible Ubuntu. j'ai donc choisi pour mon Qube (ma VM) le **template Debian 12 xfce** au lieu de Fedora 39 xfce. Car Debian est la distribution mère de Ubuntu, et aussi comme je connais mieux ^^ (ça marche peut-être aussi avec le template fedora donc, je n'ai juste pas testé)

### 2.1) Création du Qube :

Créez d'abord votre Qube (VM) pour votre wallet Dynex (conseil : clonez le Qube "untrusted" si vous ne l'avez pasutilisé), et choisissez lui le template **Debian 12 Xfce**.

### 2.2) Installation des dépendances dans le template :

Dans votre template Fedora, installez la librairie nécessaire avec cette commande dans un terminal :
`sudo apt-get install libboost-all-dev`

### 2.3) Installation du wallet :

Vous aurez besoin de Firefox pour télécharger le wallet, du gestionnaire du fichier Thunar et/ou du terminal pour extraire, le rendre exécutable et le lancer.

Si Firefox ne se lance pas, c'est lié au changement de template (Debian au lieu de Fedora). Deux possibilités pour le lancer :
- Via le terminal : `firefox-esr`
- En rafraichissant la liste des applications dans les options de votre template, puis en remplaçant Firefox par Firefox-ESR pour remettre le bon raccourci

Une fois Firefox lancé, le wallet Dynex se trouve ici : https://github.com/dynexcoin/Dynex/releases
Il y a 3 versions disponibles pour Ubuntu 22.04 (qui passent aussi sur Debian 12) :
- Dynex-main-8e9f077-ubuntu-22.04-linux-x64-**core-avx2**.zip 
- Dynex-main-8e9f077-ubuntu-22.04-linux-x64-**core2**.zip
- Dynex-main-8e9f077-ubuntu-22.04-linux-x64-**nocona**.zip (la plus ancienne, censée passer sur les CPU les plus anciens)

Celle à choisir dépend de votre CPU :

Source venant du Discord Dynex : https://discord.com/channels/1145567770872922223/1145683350967828600/1182390330763530420

>CPU instructions/compiler options...) - Nocona (oldest), Core2 (newer), AVX2 (newest CPUs)
>re: https://gcc.gnu.org/onlinedocs/gcc/x86-Options.html `-march=cpu-type`
>```
>nocona -  Improved version of Intel Pentium 4 CPU with 64-bit extensions, MMX, SSE, SSE2, SSE3 and FXSR instruction set support.
>core2 -  Intel Core 2 CPU with 64-bit extensions, MMX, SSE, SSE2, SSE3, SSSE3, CX16, SAHF and FXSR instruction set support.
>```
>https://en.wikipedia.org/wiki/Advanced_Vector_Extensions#Advanced_Vector_Extensions_2

Dedans se trouve l'exécutable dynexwallet.
Il faut le rendre exécutable (clic droit, propriétés, permissions, autoriser exécution comme un programme), ou une commande ` chmod +x dynexwallet` , c'est pareil

Ensuite y'a une librairie manquante. Pour l'installer, vous pouvez l'installer directement dans le template debian 12 xfce :
```
```
(Si vous l'installez dans le terminal du Qube dédié à Dynex, elle sera supprimée au reboot du PC et il faudra la ré-installer pour pouvoir lancer votre wallet)

Une fois installé, fermez (shutdown) le Qube du template debian 12 Xfce.
Dans l'explorateur (Thunar), normalement le wallet dynexwallet se lancedésormais en un double-clic.



