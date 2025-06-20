## Prérequis

Avant de commencer, assurez-vous d’avoir :

- Un compte Azure actif. Si vous n’avez pas encore configuré votre compte Azure, vous pouvez suivre notre [tutoriel sur la configuration de votre compte Azure](AzureAccountSetup.md).

## Vue d’ensemble des services Azure

### 1. Services de calcul
Les services de calcul Azure exécutent des applications, hébergent des sites web, gèrent des conteneurs, ou encore traitent des données.

1. **Azure Virtual Machines (VMs)**:   
Un service qui permet de créer et d'utiliser des ordinateurs virtuels sur Azure.
C’est comme louer un ordinateur dans un datacenter Microsoft que vous configurer selon vos besoins (Windows, Linux, CPU, mémoire, disque, etc.).     
📌 Exemple concret :
Vous avez un site web, une base de données ou une application qui doit tourner 24/7, mais vous ne voulez pas gérer un serveur physique chez vous ou dans vos locaux :      
✅ Solution :
Vous créez une machine virtuelle sur Azure, avec :
Windows Server 2022
4 processeurs virtuels
16 Go de RAM
256 Go de disque
Accès à distance (RDP ou SSH)

Vous pouvez ensuite :
Installer vos logiciels dessus
Y accéder à distance depuis n’importe où
L’arrêter ou la redémarrer à la demande

💰 Facturation
Vous payez à l’usage :
À l’heure ou à la seconde
Selon la taille de la VM (CPU, RAM, stockage)
Possibilité d’éteindre la VM pour économiser 

3. **Azure App Service**:    
   Un service pour deployer et pour héberger des applications web, des API ou des sites, sans avoir à gérer le serveur.
   Langages supportés: .NET, Java, Node.js, PHP, Python, Ruby    
📌 Exemple concret :        
Tu développes un petit site web en Python ou une API en Node.js.    
💡 Tu déploies ton code directement sur Azure App Service. Azure s’occupe du reste (serveur, OS, patchs...).

4. **Azure Functions**:         
Un servcie pour exécuter des extraits de code en réponse à des événements    
Un service serverless : tu écris juste le code qui doit s’exécuter quand un événement se produit, sans te soucier de l'infrastructure.          
Événements déclenchés par des uploads, des messages, des planifications (cron)     
📌 Exemple concret :       
À chaque fois qu’un fichier est ajouté dans Azure Blob Storage, tu veux analyser son contenu.
💡 Tu crées une Azure Function qui se déclenche automatiquement dès qu’un fichier est ajouté.

5. **Azure Container Instances (ACI)**: 
Un service pour exécuter un conteneur Docker, sans gérer un serveur.
Pratique pour tester des images Docker    
📌 Exemple concret :     
Tu veux tester un microservice que tu as empaqueté dans un conteneur Docker.
💡 Lance-le directement dans Azure Container Instances, sans te soucier de Kubernetes ou d'une VM.

6. **Azure Kubernetes Service (AKS)**     
Un service pour deployer, exécuter et gerer des applications conteneurisées avec Kubernetes sans avoir à gérer toute l’infrastructure.   
✅ Avantages d’AKS :
Plus besoin de gérer manuellement Kubernetes.
Azure gère les mises à jour, la sécurité, l’auto-scaling.
Intégration facile avec les autres services Azure (Azure Monitor, Azure DevOps, etc.)   

7. **Azure Batch**
Un service pour exécuter un grand nombre de tâches en parallèle (traitements lourds, calculs scientifiques, rendu vidéo...).
Gère automatiquement les VMs nécessaires
📌 Exemple concret :
Tu dois traiter 10 000 images avec un script Python.
💡 Utilise Azure Batch pour répartir le traitement sur plusieurs machines en parallèle.

8. **Azure DevTest Labs**
Un service pour créer rapidement des environnements de test ou développement, en controlant le cout afin de ne dépasser ton budget.          
📌 Exemple concret :
Ton équipe de dev veut tester différentes versions d’un logiciel sans perturber l’environnement de prod
💡 Tu crées un lab Azure où chacun a sa propre VM à usage temporaire.


### 2. Services de stockage

Il existe quatre grands types de services de stockage.        

1. **Blob Storage (Stockage d’objets)**      
Un service pour stocker et gérer de grands volumes de données non structurées telles que des images, des vidéos, des PDF, des sauvegardes etc.      
Les fichiers sont stockés sous forme de blobs (Binary Large OBjects) qui sont de trois types:  Block Blobs, Append Blobs, Page Blobs.    

2. **File Storage (Azure Files)**    
C’est un serveur de fichiers hébergé dans le cloud Azure      
✅ Idéal pour :
Remplacer un serveur de fichiers On premises
Stocker des fichiers partagés entre plusieurs équipes(le travail collaboratif)ou plusieurs applications 
Centraliser les fichiers de configuration d’une application 
Sotcker les sauvegardes   
Les utilisateurs accèdent au stockage epuis n’importe même en télétravail où comme un disque réseau (ex. : Z:\ ou \mystorageaccount.file.core.windows.net\documents) depuis Windows, macOS ou Linux via le protocole SMB. Pas besoin de VPN 

3. **Queue Storage (Stockage de files d’attente)**
Un service de files d'attente pour gérer les communications entre microservices d’une application.      
📌Cas d'utilisation : mise en file d'attente des envois d'emails de confirmation lors de la création de compte utilisateur.     
mise en file d'attente des commandes passé sur un site pour traitements par un autre microservices

4. **Table Storage (Stockage de tables)**
Un servcie pour stocker des données à structure clé-valeur mais pas forcément un schéma rigide ou relationnel 
Chaque ligne/entrée peut avoir des champs différents selon le besoin.           
📌 Exemples :
Stocker des logs ou événements générés par une application.
Gérer des profils utilisateurs simples pour une appli mobile.

📦 Caractéristiques :
Stockage NoSQL, rapide, évolutif, et économique.
Moins puissant que des bases de données classiques, mais très rapide et simple.

Exemple:  Produits dans un catalogue e-commerce
{
  "ProductID": "P1234",
  "Name": "Chaussures de sport",
  "Category": "Homme",
  "Price": 79.99,
  "InStock": true
}
Historique des commandes d’un utilisateur
{
  "OrderID": "ORD_554433",
  "UserID": "u12345",
  "OrderDate": "2025-04-20",
  "Status": "Livrée",
  "TotalAmount": 145.75
}



### 3. Services rréseaux

1. **Azure Virtual Network (VNet)**
 Un servcice pour créer un réseau virtuel privé dans Azure, comme un réseau local d’entreprise, mais hébergé dans le cloud.            
✅ Utilisé pour :Isoler et connecter des ressources Azure (VMs, bases, services...)
📌 Exemple :    
Tu crées deux VM dans Azure (serveur web + base de données)
💡 Avec un VNet, tu l'assures que tes VM sont isolés du reste du cloud Azuret, qu’elles communiquent entre elles en privé, sans passer par Internet  et que personne d'autres que toi ne peut y acceder

2. **Azure Network Security Groups (NSG)**
Un servcie pour créer des pare-feux simples qui autorisent ou bloquent le trafic réseau vers ou depuis des ressources Azure.       
✅ Utilisé pour :
Protéger les VMs et sous-réseaux
Contrôler les flux entrants/sortants
📌 Exemple :       
Tu veux qu’une VM n’accepte que le port 80 (web) et bloque le reste.
💡 Tu configures un NSG pour filtrer le trafic réseau de cette VM.

3. **Azure Load Balancer**
Un service pour répartir automatiquement le trafic réseau entrant entre plusieurs serveurs pour une meilleure disponibilité.     
✅ Utilisé pour :Équilibrer la charge réseau sur plusieurs instances    
📌 Exemple :    
Ton site web reçoit beaucoup de trafic. Tu le déploies sur 3 VMs.
💡 Azure Load Balancer répartit les visiteurs entre ces 3 serveurs pour éviter les surcharges.

 4. **Azure Application Gateway**
Un load balancer intelligent de niveau 7 (couche applicative), qui comprend les requêtes HTTP/HTTPS, les URL     
✅ Utilisé pour :   
Rediriger les requêtes selon l’URL
Terminer le SSL (HTTPS)
Protéger les applis avec le Web Application Firewall (WAF)
📌 Exemple :    
Tu as deux applis web : /client et /admin.    
💡 L’Application Gateway dirige /client vers une app A, /admin vers une app B. Il filtre aussi les attaques web grâce au WAF.

5. **Azure VPN Gateway**
Permet de créer une connexion VPN sécurisée entre ton réseau local (on-prem) et Azure.    
✅ Utilisé pour :  
Étendre ton réseau d’entreprise dans Azure
Accéder à Azure depuis ton siège ou data center    
📌 Exemple :   
Tu veux que les utilisateurs au bureau accèdent aux ressources Azure comme s’ils étaient sur le même réseau.   
💡 Tu configures une VPN Gateway pour établir un tunnel chiffré avec Azure.

6. **Azure ExpressRoute**
Une connexion privée dédiée entre Azure et ton infrastructure locale, sans passer par Internet.   
✅ Utilisé pour :    
Connexions critiques, très rapides et très fiables  
Entreprises avec besoins élevés en bande passante      
📌 Exemple :     
Une banque héberge des bases de données sensibles sur site et veut les connecter à Azure.
💡 Elle utilise ExpressRoute pour garantir fiabilité, sécurité et performance.

 7. **Azure DNS**
Un service pour gérer des noms de domaine dans Azure, comme un serveur DNS classique.         
✅ Utilisé pour :    
Gérer les noms de domaine de tes applications (ex : monapp.azurewebsites.net → IP)
Rendre tes services accessibles via des noms personnalisés
📌 Exemple :      
Tu veux que ton site soit accessible sur www.monsite.com.   
💡 Tu utilises Azure DNS pour diriger ce nom vers ton service Azure.   

8. **Azure Firewall**
Un pare-feu cloud complet, centralisé, pour protéger l’ensemble de ton réseau Azure.
✅ Utilisé pour :    
Filtrer le trafic entrant/sortant
Bloquer les IP malveillantes
Journaliser tout le trafic réseau
📌 Exemple :     
Tu veux contrôler toutes les connexions sortantes de tes VMs.   
💡 Tu places un Azure Firewall entre les VMs et Internet   

9. **Azure Front Door**
Un service d’optimisation du trafic web mondial avec accélération, WAF, caching, et HA.   
✅ Utilisé pour :
Sites à fort trafic mondial
Routage intelligent selon la géo de l’utilisateur
📌 Exemple :
Tu as des utilisateurs en Europe, Amérique, Asie.
💡 Azure Front Door les redirige automatiquement vers la région la plus proche pour un accès plus rapide.


## Exploration des services Azure

### 1. Portail Azure
1. Connectez-vous au [Portail Azure](https://portal.azure.com) à l’aide de votre compte Azure.
2. Accédez au tableau de bord, où vous trouverez une gamme de services.

### 2. Naviguer dans le tableau de bord Azure
1. Une fois connecté, vous accédez au tableau de bord Azure. Ce tableau de bord sert de hub central pour la gestion de vos ressources Azure.
2. Explorez les différentes sections, notamment « Tous les services », « Machines virtuelles », « Services d’applications », « Bases de données », etc.

### 3. Parcourir et rechercher des services
1. Cliquez sur l’option « Tous les services » dans la barre latérale gauche pour afficher la liste complète des services Azure.
2. Utilisez la barre de recherche pour trouver rapidement des services spécifiques. Par exemple, recherchez « Stockage Azure » ou « Azure App Service ».

### 4. Explorer les catégories de services
1. Les services Azure sont classés en sections telles que Calcul, Mise en réseau, Stockage, Bases de données, IA + Machine Learning, DevOps, etc.
2. Cliquez sur une catégorie qui vous intéresse pour explorer les services disponibles dans ce domaine.

### 5. En savoir plus sur les services
1. Cliquez sur un service spécifique pour accéder à sa page d’aperçu.
2. Explorez les fonctionnalités, les détails des prix, la documentation et les guides de démarrage associés au service.

## Pourquoi explorer les services Azure ?
Comprendre la vaste gamme de services Azure est crucial pour concevoir et mettre en œuvre des solutions cloud efficaces. L’exploration de divers services permettra de

