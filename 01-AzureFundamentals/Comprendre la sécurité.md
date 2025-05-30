1. **Network Security Groups (NSG)**
Un NSG est un pare-feu de base au niveau réseau. Il permet de contrôler le trafic entrant et sortant des ressources Azure comme les machines virtuelles ou les sous-réseaux.

➤ Fonctionnement :
Il utilise des règles (inbound/outbound) pour autoriser ou bloquer des connexions selon :
Adresse IP source/destination
Port (ex. : 80 pour HTTP)
Protocole (TCP/UDP)

➤ Exemple :
Autoriser le trafic HTTP (port 80) depuis Internet vers une VM.
Bloquer tout autre trafic entrant.
Utilisation typique : Sécuriser les VM ou les sous-réseaux dans un VNet.


2. **Application Security Groups (ASG)**
➤ Définition :
Les ASG permettent de regrouper des machines virtuelles par rôle ou par application (ex. : "web", "base de données") pour faciliter la gestion des règles NSG.

➤ Fonctionnement :
Au lieu de lier les règles NSG à des IP, vous les liez à des groupes logiques de machines.

➤ Exemple :
Un groupe ASG "webservers" contient toutes les VMs frontend.
Une règle NSG autorise "webservers" à parler à "dbservers" (autre ASG) sur le port 1433 (SQL Server).
Utilisation typique : Environnements avec beaucoup de VMs – simplifie la gestion.
