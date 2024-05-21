#Mettre Qubes OS sur le bon fuseau horaire

Menu Qubes OS en haut à gauche > Roue d'engrenage sur la gauche du menu > Other > Terminal Xfce

Le terminal s'ouvre, et doit avoir "Dom0" en titre de fenêtre. Si oui, saisir successiveent ces commandes (exemple ici pour l'heure Française) :
```
sudo timedatectl set-timezone 'Europe/Paris'
sudo qvm-sync-clock
exit
```

Le système se mettra à l'heure. Ça peut prendre quelques minutes.
