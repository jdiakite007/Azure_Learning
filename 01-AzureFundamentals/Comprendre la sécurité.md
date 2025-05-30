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


**Azure Security Center (Microsoft Defender for Cloud)**
Azure Security Center est une plateforme de gestion de la sécurité ans Azure (et hybride). Elle vous aide à :
Évaluer la sécurité des ressources (fournir un Secure Score de vos ressources, détecter des machines virtuelles mal configurées)
Détecter les vulnérabilités(machine virtuelles mal configuréés) => Recevoir des recommandations => Prévenir les menaces,
Renforcer la posture de sécurité de vos ressources Azure, hybrides et multicloud.

➤ Fonctions clés :
Secure Score (évaluation du niveau de sécurité)
Recommandations de configuration
Intégration avec Azure Defender pour protection avancée

➤ Exemple :
Une VM sans pare-feu est détectée → le Security Center vous alerte et propose de corriger la configuration.
💡 Utile pour tous les types d’entreprise : surveillance en temps réel, conformité ISO/GDPR.

**Azure Key Vault**
Service pour gérer et protéger les secrets, comme: mots de passe ,Clés API , Certificats, Clés de chiffrement
permet de limiter l’accès aux secrets via des rôles RBAC.
➤ Exemple :
Une application web stocke une clé d’API dans Key Vault au lieu de la mettre dans le code source.

**Azure Information Protection (AIP)**
Service de classification et de protection des documents.
➤ Fonctionnalités :
Étiquetage automatique ou manuel des documents (ex : "Confidentiel") , Chiffrement intégré , Contrôle d’accès même après partage

➤ Exemple :
Un employé télécharge un document "Confidentiel" → il est automatiquement chiffré et limité aux membres de l’organisation.
🔒AIP travaille avec Microsoft 365 pour appliquer la protection dans Word, Excel, Outlook, etc.
peut empêcher l’accès à un fichier même après l’avoir partagé à l’extérieur.


**Microsoft Defender for Identity** (ex-ATP) est conçu pour détecter en temps réél:
Les tentatives d’attaques sur les comptes d'identité (Azure AD ou AD local)
➤ Fonctions :
Analyse du trafic réseau
Détection d’activités suspectes : Pass-the-Hash, reconnaissance, exfiltration => Alertes en temps réel
➤ Exemple :
ATP détecte une tentative de connexion à répétition d’un compte admin depuis un autre pays → envoie une alerte de compromission.





