1. **Comprendre les abonnements Azure**    

Un abonnement Azure est comme un compte de facturation. Il contient :
Les ressources que tu crées (VM, bases de données, stockage…)
Les coûts liés à ces ressources
Les règles de sécurité et de gestion (comme les rôles et accès)

📌 Tu peux avoir plusieurs abonnements pour séparer les environnements (test, prod, etc.)

🔹 Contrôle d’accès (RBAC)
Tu peux contrôler qui fait quoi dans un abonnement avec des rôles (lecteur, contributeur, propriétaire).

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



