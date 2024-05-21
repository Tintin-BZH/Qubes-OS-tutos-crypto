# Tuto installation du wallet Dynex dans Qubes OS

Alors ma méthode n'est probablement pas la seule solution, mais elle marche :
Le wallet Dynex indiqué comme compatible Ubuntu. j'ai donc choisi pour mon Qube (ma VM) le **template Debian 12 xfce** au lieu de Fedora 39 xfce. Car Debian est la distribution mère de Ubuntu, et aussi comme je connais mieux ^^ (ça marche peut-être aussi avec le template fedora donc, je n'ai juste pas testé)

Créez d'abord votre Qube (VM) pour votre wallet Dynex, et choisissez lui le template Debian 12 Xfce.
Vous aurez besoin de Firefox pour télécharger le wallet, du gestionnaire du fichier Thunar et/ou du terminal pour extraire, le rendre exécutable et le lancer.

Le wallet Dynex se trouve ici : https://github.com/dynexcoin/Dynex/releases
Il y a 3 versions disponibles pour Ubuntu 22.04 (qui passent aussi sur Debian 12) :
- Dynex-main-8e9f077-ubuntu-22.04-linux-x64-**core-avx2**.zip 
- Dynex-main-8e9f077-ubuntu-22.04-linux-x64-**core2**.zip
- Dynex-main-8e9f077-ubuntu-22.04-linux-x64-**nocona**.zip

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
Dans le menu Qubes en haut à gauche, onglet templates, Debian 12 Xfce, xfce terminal, puis cette commande :
```
sudo apt-get install libboost-all-dev
```
(Si vous l'installez dans le terminal du Qube dédié à Dynex, elle sera supprimée au reboot du PC et il faudra la ré-installer pour pouvoir lancer votre wallet)

Une fois installé, fermez (shutdown) le Qube du template debian 12 Xfce.
Dans l'explorateur (Thunar), normalement le wallet dynexwallet se lancedésormais en un double-clic.
