# Ligne de commande utile Q1

Vous trouverez les commandes utiles dans se répertoire

*******
Table des matières  
 1. [Les lignes de commandes sous Windows](#LigneCommandeWindows)
 2. [Les lignes de commandes sous Linux](#LigneCommandeLinux)

*******

<div id='LigneCommandeWindows'/>

## Lignes de Commandes Utiles sous Windows 

*Commandes de base*
| Commandes        | Descriptions      
| ------|-----|
| ipconfig
| ipconfig /all
| ipconfig / ?
| route print
| dir
| cd \
| dir /Q
| dir /a
| dir /S /B /O-N /P
| mkdir
| rmdir
| copy
| copy con
| net user UserName Password /add
| net localgroup GroupeName /add
| net localgroup GrouName UserName /add
| [ ] | Signifie qu’un paramètre est optionnel |

*Ajouter des adresses*
| Commandes        | Descriptions      
| ------|-----|
| netsh interface ip add address « Ethernet » 192.168.1.99 255.255.255.0
| Pour Ipv6 : netsh interface ipv6 add address « Ethernet » 2a02 :a03f :4299 :… etc..

*Supprimer des adresses*
| Commandes        | Descriptions      
| ------|-----|
| netsh interface ip delete address « Ethernet » 192.168.1.99
| Pour Ipv6 : netsh interface ipv6 delete address « Ethernet » 2a02…Etc…

*Configuration dynamique "DHCP"*
| Commandes        | Descriptions      
| ------|-----|
| netsh interface ip set address « Ethernet » dhcp
| ipconfig /release
| ipconfig /renew

*Serveur DNS*
| Commandes        | Descriptions     
| ------|-----|
| netsh interface ip set dns « Ethernet » static 192.168.1.1
| netsh interface ip add dns « Ethernet » 8.8.8.8
| netsh interface ip set dns Ethernet dhcp

*Activer/désactiver une carte réseau*
| Commandes        | Descriptions      
| ------|-----|
| netsh interface set interface « Ethernet » enable
| netsh interface set interface « Ethernet » disable

*Vérifier/supprimer/configurer le default gateway en IPv4*
| Commandes        | Descriptions      
| ------|-----|
| route print
| route add [-p] 0.0.0.0 192.168.1.1
| route delete 0.0.0.0

<div id='LigneCommandeLinux'/>

## Lignes de Commandes Utiles sous Linux

*Commandes de base*
| Commande        | Description      
| ------|-----|
| mkdir
| rm
| touch
| mv
| echo
| passwd
| date
| ls
| su -
| file /chemin
| head
| tail
| wc
| vim
| nano
| cat
| sudo useradd UserName -u 7777 -m -d /home/UserName -s /bin/bash -c "Commentaire"
| sudo passwd UserName
| sudo nano /etc/sudoers (Allow members to execute Sudo command) UserName ALL=(ALL:ALL) ALL
| sudo id > fichierDeDestination

*Configurer le clavier :*
| Commande        | Description      
| ------|-----|
| setxkbmap be

*Commmandes réseau*
| Commande        | Description      
| ------|-----|
| ip addr show (ip -6 addr show)
| ip link show
| ip route show

*Cat affiche le contenue du fichier voici un exemple*
| Commande        | Description      
| ------|-----|
| cat /etc/resolv.conf

*Copie d’un fichier grâce à la commande cp*
| Commande        | Description      
| ------|-----|
| cp /etc/network/interfaces /etc/network/interfaces.sav

*Redémarrage complet du service réseau*
| Commande        | Description      
| ------|-----|
| systemctl restart networking
