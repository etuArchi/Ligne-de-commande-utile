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
| mkdir | Crée un nouveau répertoire (dossier)
| rm | Supprime des fichiers ou des répertoires. Faites attention, car cette commande est irréversible.
| touch | Crée un fichier vide ou actualise la date de modification d'un fichier existant.
| mv | Déplace ou renomme des fichiers et des répertoires.
| echo | Affiche du texte à la sortie standard (généralement le terminal) ou redirige le texte vers un fichier.
| passwd | Permet à un utilisateur de changer son mot de passe.
| date | Affiche la date et l'heure actuelles.
| ls | Liste les fichiers et répertoires dans le répertoire courant.
| su - | Permet de passer à l'utilisateur root (superutilisateur) avec son environnement.
| file /chemin | Détermine le type de fichier pour le chemin spécifié.
| head | Affiche les premières lignes d'un fichier.
| tail | Affiche les dernières lignes d'un fichier.
| wc | Affiche le nombre de lignes, de mots et de caractères d'un fichier.
| vim | Ouvre l'éditeur de texte Vim.
| nano | Ouvre l'éditeur de texte Nano.
| cat | Concatène et affiche le contenu des fichiers.
| sudo useradd UserName -u 7777 -m -d /home/UserName -s /bin/bash -c "Commentaire" | Ajoute un nouvel utilisateur avec des options spécifiées telles que l'UID, le répertoire personnel, le shell, etc.
| sudo passwd UserName | Permet de définir un mot de passe pour l'utilisateur spécifié.
| sudo nano /etc/sudoers (Allow members to execute Sudo command) UserName ALL=(ALL:ALL) ALL | Modifie le fichier sudoers pour accorder des droits sudo à un utilisateur spécifié. 
| sudo id > fichierDeDestination | Exécute la commande 'id' en tant qu'utilisateur root et redirige la sortie vers un fichier.

*Configurer le clavier :*
| Commande        | Description      
| ------|-----|
| setxkbmap be | Cette commande définira la disposition du clavier sur "be", indiquant la disposition belge.

*Commmandes réseau*
| Commande        | Description      
| ------|-----|
| ip addr show (ip -6 addr show) | Cette commande affiche les informations sur les interfaces réseau et leurs adresses IP associées. L'option '-6' permet de filtrer spécifiquement les adresses IPv6.
| ip link show | Cette commande affiche des informations sur toutes les interfaces réseau disponibles, telles que leur état (activé ou désactivé), leur adresse MAC, et d'autres détails.
| ip route show | Cette commande affiche la table de routage du système, montrant les itinéraires possibles pour atteindre différentes destinations réseau.

*Cat affiche le contenue du fichier voici un exemple*
| Commande        | Description      
| ------|-----|
| cat /etc/resolv.conf | Cette commande affiche le contenu du fichier /etc/resolv.conf. Ce fichier est utilisé pour configurer les paramètres de résolution DNS sur le système. En particulier, il indique les adresses des serveurs DNS utilisés par le système pour résoudre les noms de domaine en adresses IP.

*Copie d’un fichier grâce à la commande cp*
| Commande        | Description      
| ------|-----|
| cp /etc/network/interfaces /etc/network/interfaces.sav | Cette commande copie le contenu du fichier /etc/network/interfaces vers un nouveau fichier nommé /etc/network/interfaces.sav. Cela crée une sauvegarde du fichier d'interfaces réseau actuel.

*Redémarrage complet du service réseau*
| Commande        | Description      
| ------|-----|
| systemctl restart networking | Cette commande redémarre le service responsable de la gestion des interfaces réseau et de la configuration du réseau.

>*La commande ifdown enp0s3 déconfigure votre interface enp0s3.<br>
La commande ifup enp0s3 configure votre interface enp0s3.<br>
La commande ifquery enp0s3 vous renvois la liste des paramètres liés à l’interface enp0s3 dans le fichier interfaces.*

*Supprimer la config d’une interface*
| Commande        | Description      
| ------|-----|
| ip addr flush dev enp0s3 | Cette commande supprime toutes les adresses IP associées à l'interface réseau spécifiée 'enp0s3'. Elle efface toutes les configurations d'adresses IPv4 liées à cette interface.
| ip -6 addr flush dev enp0s3 | Cette commande supprime toutes les adresses IPv6 associées à l'interface réseau spécifiée 'enp0s3'. Elle efface toutes les configurations d'adresses IPv6 liées à cette interface.

*Démarrer un process client DHCP*
| Commande        | Description      
| ------|-----|
| dhclient -v enp0s3 | Cette commande utilise le client DHCP ('dhclient') pour demander une adresse IP au serveur DHCP sur l'interface réseau spécifiée 'enp0s3'. L'option '-v' (verbose) affiche des informations détaillées pendant le processus de demande d'adresse IP.

*Terminer tous les process de type dhclient*
| Commande        | Description      
| ------|-----|
| pkill dhclient | Cette commande envoie un signal pour terminer tous les processus 'dhclient' en cours d'exécution sur le système. Elle met fin aux instances du client DHCP qui sont actuellement actives.

*Le changement du hostname « à chaud » et de manière temporaire peut se faire avec la 
commande*
| Commande        | Description      
| ------|-----|
| hostname MonNouvelHostname | Cette commande change le nom d'hôte du système à "MonNouvelHostname". Le nom d'hôte est un identifiant unique attribué à un périphérique sur un réseau. 

*Installez les utilitaires DNS avec la commande*
| Commande        | Description      
| ------|-----|
| apt-get install dnsutils | Cette commande utilise le gestionnaire de paquets 'apt-get' pour installer le paquet 'dnsutils'. Le paquet 'dnsutils' contient des utilitaires liés aux services DNS, tels que 'nslookup'.
| nslookup www.google.be (vérifiez que la résolution de nom fonctionne avec la commande nslookup) | Cette commande utilise l'outil 'nslookup' pour interroger les serveurs DNS et obtenir des informations sur la résolution de nom du site web 'www.google.be'. Elle affiche généralement l'adresse IP associée au nom de domaine spécifié.
