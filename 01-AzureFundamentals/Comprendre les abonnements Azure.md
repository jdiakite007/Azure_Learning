1. **Comprendre les abonnements Azure**    

Un abonnement Azure est comme un compte de facturation.
Il contient :
Les ressources que tu crées : machines virtuelles (VM), bases de données, réseaux, etc.
Les coûts liés à ces ressources (c’est ce qui est facturé)
Les règles de sécurité et de gestion, comme les rôles d’accès (RBAC)

📌 Tu peux avoir plusieurs abonnements pour séparer :
Environnements (test, production, développement)
Projets ou équipes


2. Contrôle d’accès dans Azure – RBAC
🔹 RBAC = Role-Based Access Control
➡️ C’est un système qui permet de gérer qui a le droit de faire quoi dans Azure.

Tu attribues un rôle à un utilisateur ou groupe sur :
Un abonnement
Un groupe de ressources
Une ressource spécifique (ex : une VM)

🔐 Rôles RBAC principaux :
Rôle	                      Ce qu’il peut faire
Lecteur	🔎                 Voir les ressources, mais ne peut rien modifier
Contributeur	                 🛠️ Créer et modifier les ressources (mais ne peut pas donner des accès)
Propriétaire	👑               A tous les droits, y compris la gestion des accès


🧩 Exemple concret :
Tu veux que :
Julie puisse voir les machines virtuelles → Donne-lui le rôle de Lecteur
Karim puisse créer et modifier des ressources → Donne-lui le rôle de Contributeur
Sarah puisse gérer tout, y compris donner des accès → Donne-lui le rôle de Propriétaire

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
Réponse : 
Le rôle Contributeur peut créer et modifier des ressources mais ne peut pas gérer les accès ou les rôles.

Qui peut gérer les accès aux ressources ?
Réponse : C
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



