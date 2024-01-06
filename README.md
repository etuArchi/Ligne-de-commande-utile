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
| copy con | Permet de créer un nouveau fichier en saisissant du texte dans la console. Vous pouvez appuyer sur Ctrl+Z pour terminer.
| net user UserName Password /add | Ajoute un nouvel utilisateur avec le nom d'utilisateur spécifié et le mot de passe.
| net localgroup GroupeName /add | Crée un nouveau groupe local.
| net localgroup GrouName UserName /add | Ajoute un utilisateur existant à un groupe local.
| [ ] | Signifie qu’un paramètre est optionnel | Indique que le paramètre entre crochets est facultatif et peut être inclus ou omis selon les besoins.

*Ajouter des adresses*
| Commandes        | Descriptions      
| ------|-----|
| netsh interface ip add address « Ethernet » 192.168.1.99 255.255.255.0 | Cette commande ajoute une adresse IP statique (IPv4) à l'interface réseau nommée "Ethernet". Elle utilise l'adresse IP 192.168.1.99 avec un masque de sous-réseau de 255.255.255.0.
| Pour Ipv6 : netsh interface ipv6 add address « Ethernet » 2a02 :a03f :4299 :… etc.. | Cette commande ajoute une adresse IPv6 à l'interface réseau nommée "Ethernet". L'adresse IPv6 spécifiée (2a02:a03f:4299:...etc.) doit être une adresse valide dans le format IPv6.

*Supprimer des adresses*
| Commandes        | Descriptions      
| ------|-----|
| netsh interface ip delete address « Ethernet » 192.168.1.99 | Cette commande supprime l'adresse IP spécifiée (192.168.1.99) de l'interface réseau nommée "Ethernet" en IPv4. Elle est utilisée pour retirer une adresse IPv4 de l'interface.
| Pour Ipv6 : netsh interface ipv6 delete address « Ethernet » 2a02…Etc… | Cette commande supprime l'adresse IPv6 spécifiée (2a02...Etc.) de l'interface réseau nommée "Ethernet" en IPv6. Elle est utilisée pour retirer une adresse IPv6 de l'interface.

*Configuration dynamique "DHCP"*
| Commandes        | Descriptions      
| ------|-----|
| netsh interface ip set address « Ethernet » dhcp | Cette commande configure l'interface réseau nommée "Ethernet" pour utiliser DHCP (Dynamic Host Configuration Protocol) afin d'obtenir une adresse IP automatiquement. Cela signifie que l'adresse IP sera attribuée dynamiquement par un serveur DHCP.
| ipconfig /release | Cette commande libère la configuration IP actuelle de toutes les interfaces réseau de votre système. Elle informe le serveur DHCP que l'adresse IP n'est plus utilisée.
| ipconfig /renew | Cette commande renouvelle la configuration IP de toutes les interfaces réseau de votre système. Elle demande au serveur DHCP une nouvelle adresse IP.

*Serveur DNS*
| Commandes        | Descriptions     
| ------|-----|
| netsh interface ip set dns « Ethernet » static 192.168.1.1 | Cette commande configure l'interface réseau nommée "Ethernet" pour utiliser une adresse DNS statique. Dans cet exemple, l'adresse DNS statique est définie sur 192.168.1.1.
| netsh interface ip add dns « Ethernet » 8.8.8.8 | Cette commande ajoute une adresse DNS à l'interface réseau nommée "Ethernet". Dans cet exemple, l'adresse DNS ajoutée est 8.8.8.8 (qui est l'un des serveurs DNS publics de Google).
| netsh interface ip set dns Ethernet dhcp | Cette commande configure l'interface réseau nommée "Ethernet" pour utiliser DHCP (Dynamic Host Configuration Protocol) pour l'attribution automatique des serveurs DNS. Cela signifie que les serveurs DNS seront attribués dynamiquement par un serveur DHCP.

*Activer/désactiver une carte réseau*
| Commandes        | Descriptions      
| ------|-----|
| netsh interface set interface « Ethernet » enable | Cette commande active l'interface réseau spécifiée "Ethernet". Elle permet à l'interface de commencer à recevoir et envoyer des données.
| netsh interface set interface « Ethernet » disable | Cette commande désactive l'interface réseau spécifiée "Ethernet". Elle empêche l'interface de recevoir ou d'envoyer des données, la mettant ainsi hors service.

*Vérifier/supprimer/configurer le default gateway en IPv4*
| Commandes        | Descriptions      
| ------|-----|
| route print | Cette commande affiche la table de routage du système, montrant les itinéraires possibles pour atteindre d'autres réseaux.
| route add [-p] 0.0.0.0 192.168.1.1 | Cette commande ajoute une route par défaut vers l'adresse IP spécifiée (192.168.1.1) dans la table de routage. Cela signifie que tout le trafic destiné à des destinations inconnues sera dirigé vers cette passerelle.
| route delete 0.0.0.0 | Cette commande supprime la route par défaut de la table de routage. Cela pourrait être utilisé lorsque vous ne souhaitez plus diriger tout le trafic vers une passerelle spécifique.

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
