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

**User Defined Routes (UDR)**    
➤ Définition :
Les UDR sont des routes personnalisées que vous pouvez définir pour le trafic réseau dans un VNet.

➤ Fonctionnement :
Azure crée des routes automatiquement, mais vous pouvez :
Rediriger le trafic vers une appliance réseau (pare-feu, NVA).
Forcer le passage par un chemin précis.

➤ Exemple :
Tout le trafic sortant d’un sous-réseau passe d’abord par un Azure Firewall.
Utilisation typique : Scénarios de sécurité avancés ou architectures avec inspection réseau.

**Azure Firewall**
➤ Définition :
Azure Firewall est un pare-feu cloud managé, hautement disponible, avec filtrage réseau et application.

➤ Fonctionnalités :
Inspection du trafic sortant et entrant.

Règles DNS, FQDN (noms de domaine).

Intégration avec Azure Monitor pour les logs.

➤ Exemple :
Bloquer tout trafic sortant sauf vers les domaines *.microsoft.com.
Journaliser toutes les connexions refusées.
Utilisation typique : Protection centrale pour l’ensemble d’un réseau Azure (plus avancée que NSG).

**Azure DDoS Protection**
➤ Définition :
Protection contre les attaques par déni de service distribué (DDoS) qui cherchent à submerger un service et le rendre indisponible.

➤ Niveaux :
Basic : activé par défaut – protection de base.
Standard : protection avancée, alertes, analyses post-attaque, SLA.

➤ Exemple :
Une application web critique subit une attaque DDoS : Azure DDoS Standard absorbe le trafic anormal.
Utilisation typique : Applis critiques, e-commerce, services publics.
