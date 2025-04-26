## Prérequis

Avant de commencer, assurez-vous d’avoir :

- Un compte Azure actif. Si vous n’avez pas encore configuré votre compte Azure, vous pouvez suivre notre [tutoriel sur la configuration de votre compte Azure](AzureAccountSetup.md).

## Vue d’ensemble des services Azure

Azure offre une vaste gamme de services conçus pour répondre aux divers besoins des entreprises. Dans ce tutoriel, nous allons explorer quelques catégories de services de base :

### 1. Services de calcul

- **Machines virtuelles** : Lancez et gérez des instances virtualisées de systèmes d’exploitation.
- **Azure App Service** : déployez et hébergez des applications web sans gérer l’infrastructure 
- **Azure Functions** : Exécutez des extraits de code en réponse à des événements

### 2. Services de stockage

Sur Microsoft Azure, il existe quatre grands types de services de stockage, chacun adapté à des besoins différents.

1. Blob Storage (Stockage d’objets)      
✅ Idéal pour : Stocker des fichiers non structurés, telles que des images, desvidéos, des PDF,des sauvegardes etc.    
📌 Exemples :
Sauvegarder des vidéos d'une caméra de surveillance,stocker des images pour un site web,héberger des backups d'applications.         
📦 Caractéristiques : Gèrer de grands volumes de données non structurées.    

Les fichiers sont stockés sous forme de blobs (Binary Large OBjects) qyuiu sont de trois types:  Block Blobs, Append Blobs, Page Blobs.    

2. File Storage (Stockage de fichiers Azure Files)     
📁 Azure Files = serveur de fichiers dans le cloud     

✅ Idéal pour : Remplacer un serveur de fichiers On premises: C’est comme un serveur de fichiers mais hébergé sur Azure, pour paratger des fichiers entre applications     
📦 Caractéristiques :    
✅ Accès facile, comme un disque réseau.    
🔐 Sécurisé, scalable et sans maintenance.   
🧰 Parfait pour le travail collaboratif, les sauvegardes ou les logiciels métiers.    
Les utilisateurs accèdent au stockage comme un disque réseau (ex. : Z:\ ou \mystorageaccount.file.core.windows.net\documents) depuis Windows, macOS ou Linux via le protocole SMB     
Pas besoin de VPN : possibilité d’accès depuis n’importe où, même en télétravail.   

📌 Exemples :
Stocker des fichiers bureautiques partagés entre plusieurs équipes.
Centraliser les fichiers de configuration d’une application.


4. Queue Storage (Stockage de files d’attente)
✅ Idéal pour : Gérer la communication entre différentes parties d’une application, de manière asynchrone.
📌 Exemples :
Une application web envoie un message à une queue pour lancer une tâche en arrière-plan.
Une commande passée sur un site est placée dans un stockage defile d'attente pour traitement par un autre service.
📦 Caractéristiques :
Utilisé pour échanger des messages entre services/applications.
Chaque message peut faire jusqu'à 64 Ko.

5. Table Storage (Stockage de tables)
✅ Idéal pour : Stocker des données NoSQL à strucutre flexible organisées par paires clé-valeur, souvent sous forme de JSON.
Ce sont des données qui ont une structure clé-valeur mais pas forcément un schéma rigide ou relationnel.

Chaque ligne/entrée peut avoir des champs différents selon le besoin.
📌 Exemples :
Stocker des logs ou événements générés par une application.
Gérer des profils utilisateurs simples pour une appli mobile.
Suivre les états d’objets connectés dans un système IoT.
📦 Caractéristiques :
Stockage NoSQL, rapide, évolutif, et économique.
Clés de partition et de ligne pour organiser les données.
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








- **Stockage Blob Azure** : stockez et gérez des données non structurées, telles que des images, des documents et des sauvegardes.
- **Azure Table Storage** : Stockez des données NoSQL structurées (fichiers TAML, code CSS)
- **Stockage de file d’attente Azure** : créez des applications évolutives en déchargeant le travail dans une file d’attente.
- **File Storage** : 

### 3. Services de réseautage

- **Réseau virtuel Azure** : créez des réseaux isolés pour gérer la communication des machines virtuelles.
- **Azure Load Balancer** : répartissez le trafic réseau entrant vers les ressources pour une meilleure disponibilité.
- **Passerelle VPN Azure** : établissez des connexions sécurisées entre les réseaux locaux et Azure.

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
