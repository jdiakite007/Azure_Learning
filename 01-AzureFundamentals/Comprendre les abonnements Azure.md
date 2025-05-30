1. **Comprendre les abonnements Azure**    

Un abonnement Azure est comme un compte de facturation.
Il contient :
Les ressources que tu crées : machines virtuelles (VM), bases de données, réseaux, etc.
Les coûts liés à ces ressources (c’est ce qui est facturé)
Les règles de sécurité et de gestion, comme les rôles d’accès (RBAC)

📌 Tu peux avoir plusieurs abonnements pour séparer :
Environnements (test, production, développement)
Projets ou équipes    


**Contrôle d’accès dans Azure – RBAC** ou Role-Based Access Control
➡️ C’est un système qui permet de gérer qui a le droit de faire quoi dans Azure.

**Scope ou portée**
Azure permet d'attribuer des rôles RBAC à un utilisateur ou groupe à trois niveaux:
L’abonnement (toutes les ressources)
Le groupe de ressources (ensemble logique de ressources)
Une ressource individuelle (VM, base de données…)


🔐 Rôles RBAC principaux :

Lecteur: peut voir les ressources, lire la configuration, voir les métriques et journaux mais ne peut rien modifier ou créer quoi que ce soit
Idéal pour les auditeurs, les observateurs, ou pour superviser sans risque.
Contributeur: peut créer, modifier et supprimer les ressources (mais ne peut pas donner des accès)
Propriétaire: peut tout faire, y compris la gestion des accès RBAC

🧩 Exemple concret :
Tu veux que :
Julie puisse voir les machines virtuelles → Donne-lui le rôle de Lecteur
Karim puisse créer et modifier des ressources → Donne-lui le rôle de Contributeur
Sarah puisse gérer tout, y compris donner des accès → Donne-lui le rôle de Propriétaire

 Attribuer un rôle RBAC dans Azure (via le Portail Azure)
📍 Étapes simples :
Connecte-toi au portail Azure
👉 https://portal.azure.com
Va sur la ressource concernée
(exemple : une VM, un groupe de ressources, ou un abonnement)
Clique sur "Contrôle d’accès (IAM)" dans le menu de gauche
Clique sur "Ajouter" ➜ "Ajouter une attribution de rôle"
Dans la fenêtre qui s’ouvre :
Sélectionne le rôle que tu veux attribuer (ex : Lecteur, Contributeur, Propriétaire)
Clique sur "Suivant"
Sélectionne l’utilisateur ou le groupe à qui tu veux attribuer le rôle
Tu peux rechercher un utilisateur, un groupe, ou un principal de service (application)
Clique sur "Vérifier + attribuer"
✅ C’est fait ! Le rôle est désormais appliqué à la bonne portée.



🗂️ En résumé pour AZ-900 :
Concept	Description simple
Abonnement Azure	Contient les ressources, coûts et règles d’accès
RBAC	Contrôle qui (utilisateur, groupe etc..) peut faire quoi (Lecteur, Contributeur, Propriétaire) sur quellle scope ou portée  dans Azure
Rôles principaux	Lecteur, Contributeur, Propriétaire
Portée possible	:Abonnement, groupe de ressources ou ressource unique

Exercies:
Quel rôle permet uniquement de voir sans modifier ?
Le rôle Lecteur permet uniquement de consulter les ressources sans pouvoir les modifier.

Quel rôle permet de créer et modifier mais pas gérer les accès ?
Le rôle Contributeur peut créer et modifier des ressources mais ne peut pas gérer les accès ou les rôles.

Qui peut gérer les accès aux ressources ?
Le rôle Propriétaire a tous les droits, y compris la gestion des accès.

🔹 Types d’offres Azure
**Free** : pour tester gratuitement
**Pay-As-You-Go** : Paiement selon ce que vous consommez => tu payes selon l’utilisation 
**Enterprise Agreement (EA)** : pour grandes entreprises
**MSDN / Visual Studio** : pour les développeurs

**Groupes de gestion (Management Groups)**
Tu peux organiser plusieurs abonnements dans des groupes hiérarchiques pour :
Appliquer des règles ou politiques globales
Gérer l’accès ou les coûts à grande échelle

Exemple :

Entreprise
 └── Groupe management : Production
       └── Abonnement 1 (Appli A)
       └── Abonnement 2 (Appli B)

**Planification et gestion des coûts**
🛒 Options d’achat :
Directement via le portail Azure
Via un revendeur ou contrat entreprise
Avec une carte de crédit pour Pay-As-You-Go

**Compte gratuit Azure**
Tu obtiens 200 $ de crédit pendant 30 jours
Puis, certains services restent gratuits pendant 12 mois
Exemples : Machines virtuelles B1S, stockage 5 Go, etc.
🧠 Idéal pour s’entraîner ou apprendre sans payer

**Facteurs qui influencent les coûts**

Type de ressource:	Une VM coûte plus qu’un stockage
Région:	Les prix varient selon le lieu (ex : Europe vs US)
Ingress / Egress:	Ingress = gratuit / Egress (sortie de données) = payant
Taille:	Plus la VM est puissante, plus elle coûte
Durée	:Si elle tourne 24/7, elle coûte plus que 2h/jour

🧾 7. Zones de facturation
Azure utilise des zones géographiques pour la facturation

Par exemple, les transferts de données entre régions différentes sont facturés

**Azure Pricing Calculator**
📍 Site : https://azure.com/pricing/calculator
Azure Pricing Calculator** ➡ Sert à **prévoir les coûts** en fonction des ressources choisies. 
Il permet de :
Estimer le coût d’un projet Azure
Choisir les ressources, tailles, durées
Obtenir une estilation du cout mensuel des servcies 


**TCO Calculator (Coût total de possession)**
📍 Site : https://azure.com/tco
Un outil pour comparer combien coûte ton infrastructure actuelle (on-premise) avec combien cela coûterait sur Azure.
Il permet d'estimer les économies que tu peux faire en migrant les ressources sur Azure
Utilisé pour aider à convaincre une entreprise de migrer vers Azure

💵 10. Bonnes pratiques pour réduire les coûts

**Analyse des coûts et créer des budgets** (Azure cost managmenet)
**Créer des alertes**	 pour etre averti quand on dépasse un seuil
**Utiliser les tags** pour 	marquer les ressources par projet ou équipe pour mieux analyser et suivre les dépenses
**Azure Reservations**	Réserver des ressources à l’avance (1 an, 3 ans) pour avoir jusqu’à 70 % d’économies
**Azure Advisor**	Recommandations automatiques pour optimiser les coûts

**Azure Cost Management**
Un outil pour: 
Suivre les dépenses en temps réel
Créer des budgets personnalisés
Définir des alertes lorsqu’un budget est dépassé ou presque atteint
Analyser la répartition des coûts par ressource, projet, ou service
Ooptimiser les dépenses

👉 C’est l’outil principal pour gérer les coûts et éviter les mauvaises surprises sur ta facture Azure.
📌 Accessible depuis le portail Azure > Cost Management + Billing



