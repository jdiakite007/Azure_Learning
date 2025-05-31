**Azure Governance**

La gouvernance Azure, c’est un **ensemble de règles** et **d’outils** qui te permettent de :    
✅ Organiser    
✅ Contrôler     
✅ Sécuriser     
✅ Surveiller     
...tes ressources cloud de **manière structurée** et **conforme aux règles de l’entreprise**.    

C'est comme une charte de bonne conduite + boîte à outils pour organiser, sécuriser, et contrôler tes ressources Cloud.   

**Pourquoi c’est important** ?   
Sans gouvernance, on risque :    
Le chaos dans les ressources: chacun peut faire ce qu'il veut    
Du gaspillage de budget    
Des risques de sécurité    
Le non-respect des lois ou politiques internes    

Avec une bonne gouvernance :
✅ Les règles sont claires
✅ Les accès sont bien gérés
✅ Les ressources sont bien utilisées
✅ L’entreprise est conforme aux normes      


**Tableau des outils de gouvernance Azure**
|  Outil	        |  Rôle principal                 |    Exemple    |
|-----------------|----------------                 |----------------|
| Azure Policy   | Appliquer automatiquement des règles	  | Interdire le déploiement de VMs hors d'Europe    |
| RBAC (Role-Based Access Control)	   | Gérer qui peut faire quoi   | Un développeur peut lire une base mais pas la supprimer   |
|Locks   |Bloquer les modifications ou suppressions   |Empêcher la suppression d’une ressource critique  |
|Azure Advisor	  |Recommander des améliorations  |Suggère de supprimer une VM qui ne sert plus  |
|Blueprints	  |Déployer des environnements prédéfinis  |Créer un environnement complet (réseau + règles + VMs) d’un coup |

 **Les outils principaux de la gouvernance Azure :**

1. **Azure Policy**
Azure Policy te permet de **créer et appliquer des règles automatiques (policy) sur tes ressources** pour qu’elles **respectent les standards et conformités** de
C’est un contrôle de conformité en temps réel.
Définit des règles pour les actions autorisées, interdites ou obligatoires dans un environnement Azure.
📌 Exemples de politiques Azure :
🌐 Politique	🛠️ Effet
❌ Interdire les déploiements de ressources hors de "France Central"	=> Empêcher les utilisateurs de créer des ressources ailleurs
🔒 Chiffrement obligatoire des disques de toutes leds VM => 	Forcer l’activation du chiffrement au niveau de la VM
🏷️ Vérifier la présence de tags => 	S’assurer que chaque ressource est bien étiquetée (ex : prod/dev/test)
📎 Forcer un SKU spécifique pour les VMs (ex : taille D2s)	=> Contrôler les types autorisés
🔄 Auditer l’usage d’un service obsolète	=> Génère des alertes sans bloquer
📌 Exemples :
|  Policy      |  Effet                |   
|-----------------|----------------    |
| Interdire les déploiements de ressources hors de "France Central   |  Empêcher les utilisateurs de créer des ressources ailleurs  |
| Chiffrement obligatoire des disques de toutes leds VM | Forcer l’activation du chiffrement au niveau de la VM  | 
|Vérifier la présence de tags|S’assurer que chaque ressource est bien étiquetée (ex : prod/dev/test)  |
|Forcer un SKU spécifique pour les VMs (ex : taille D2s) |Contrôler les types autorisés |
|Auditer l’usage d’un service obsolète  |Génère des alertes sans bloquer |

🔹 Initiative :
Groupe de plusieurs politiques → utile pour appliquer un ensemble cohérent de règles.
🧠 Retenir : Policy = une règle, Initiative = plusieurs règles

2. **Role-Based Access Control (RBAC)**
Définir qui peut faire quoi sur quelles ressources Azure.
🔐 Principe :
Qui : un utilisateur, un groupe ou un service
Quoi : action autorisée (lire, modifier, supprimer)
Où : portée (abonnement, groupe de ressources, ressource)

📌 Rôles prédéfinis :
Owner : tout faire, y compris accorder des accès
Contributor : créer/modifier, mais pas gérer les accès
Reader : lecture seule


3. **Azure Locks (Verrous)**

| Lock        |  Rôle principal                 |    Exemple    |
|-----------------|----------------                 |----------------|
|CanNotDelete  | modification mais pas suppression  |Empêcher qu’un compte de stockage critique soit supprimé par erreur|
| ReadOnly    | lecture mais pas modification ou suppression   | Un développeur peut lire une base mais pas la supprimer   |


5. **Azure Advisor** 
C'est un outils gratuit qui t’aide à **améliorer ton environnement Azure** 
Il analyse automatiquement tes ressources et te donne des recommandations pour améliorer leur :   
🔒 Sécurité  Ex: Activer Azure Defender, corriger des ports ouverts   
⚙️ Haute disponibilité    Ex: Des ressources ne sont pas redondées	 => Ajouter des groupes de disponibilité pour les VMs critiques
⚡ Performance   Ex: Passer une base de données lente sur un niveau supérieur
💰 Coût   Ex: Supprimer des disques non utilisés, réduire la taille d’une VM pour économiser, stopper une VM inutilisée
🧰 Excellence opérationnelle   Ex: Mettre à jour les tags, organiser les ressources, planifier les sauvegardes



5. **Azure Blueprints**
Permet de déployer un ensemble complet de ressources + règles de gouvernance en un seul modèle.
Créer un modèle prêt à l’emploi avec règles + ressources

Contenu possible d’un Blueprint :
Groupes de ressources
Rôles RBAC
Stratégies Azure Policy
Modèles ARM (infrastructure)


📌 Exemple :
Créer un environnement “Production” avec :
Une stratégie de chiffrement obligatoire
Un rôle Contributor attribué
Un tag automatique appliqué

💡 BluePrint = modèle de déploiement + conformité intégré
Vous devez créer un environnement standardisé (avec un groupe de ressources, des rôles RBAC, et des stratégies). Quelle solution utiliser ?
✅ Réponse attendue : Azure Blueprints, qui permet de déployer tous ces éléments de façon cohérente.


**Exemples concrets de gouvernance**
Tu veux :
Empêcher que des ressources soient supprimées accidentellement → Utilise Locks
Créer un environnement “prêt à l’emploi” pour ton équipe projet → Utilise Blueprints
Appliquer automatiquement les règles de sécurité et de conformité → Utilise Azure Policy
Limiter ce que chaque utilisateur peut faire dans Azure → Utilise RBAC
Améliorer la sécurité et les performances → Suis les conseils d’Azure Advisor


