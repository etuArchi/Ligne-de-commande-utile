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
| ipconfig | Affiche l'adresse IP, le masque de sous-réseau et la passerelle pour toutes les interfaces réseau de votre machine.
| ipconfig /all | Affiche des informations détaillées sur toutes les interfaces réseau, y compris les adresses physiques (MAC), les serveurs DNS, etc.
| ipconfig / ? | Affiche l'aide pour la commande ipconfig, montrant comment utiliser différentes options avec celle-ci.
| route print | Affiche la table de routage, montrant les itinéraires possibles pour atteindre d'autres réseaux.
| dir | Liste les fichiers et dossiers dans le répertoire courant.
| cd \ | Change le répertoire de travail vers la racine du lecteur
| dir /Q | Affiche les propriétaires des fichiers et des répertoires
| dir /a | Affiche tous les fichiers, y compris les fichiers cachés et les dossiers spéciaux.
| dir /S /B /O-N /P | Liste tous les fichiers de manière récursive (/S), affiche le résultat sous forme de chemin complet (/B), trie les résultats par ordre alphabétique inversé (/O-N) et affiche une page à la fois (/P).
| mkdir | Crée un nouveau répertoire
| rmdir | Supprime un répertoire vide.
| copy | Copie un fichier d'un emplacement à un autre.
| copy con | 
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

>*La commande ifdown enp0s3 déconfigure votre interface enp0s3.<br>
La commande ifup enp0s3 configure votre interface enp0s3.<br>
La commande ifquery enp0s3 vous renvois la liste des paramètres liés à l’interface enp0s3 dans le fichier interfaces.*

*Supprimer la config d’une interface*
| Commande        | Description      
| ------|-----|
| ip addr flush dev enp0s3
| ip -6 addr flush dev enp0s3

*Démarrer un process client DHCP*
| Commande        | Description      
| ------|-----|
| dhclient -v enp0s3

*Terminer tous les process de type dhclient*
| Commande        | Description      
| ------|-----|
| pkill dhclient

*Le changement du hostname « à chaud » et de manière temporaire peut se faire avec la 
commande*
| Commande        | Description      
| ------|-----|
| hostname MonNouvelHostname

*Installez les utilitaires DNS avec la commande*
| Commande        | Description      
| ------|-----|
| apt-get install dnsutils
| nslookup www.google.be (vérifiez que la résolution de nom fonctionne avec la commande nslookup)
