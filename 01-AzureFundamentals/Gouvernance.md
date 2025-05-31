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
Azure Policy permet de **créer et appliquer des règles (policy) en temps réel sur tes ressources** pour s'asdsurer qu’elles **respectent les standards et conformités** de l'entreprise

Azure Policy =  Contrôle de conformité en temps réel + Actions bloquantes ou correctrices => Automatiser la conformité des ressources

En cas de non conformité:     
La réaction d’Azure Policy dépend de l’effet que tu as défini dans la règle.     

Voici les comportements possibles👇    

🛑 Effet : Deny (refus)
Résultat : Le déploiement de la ressource est bloqué.
📌 C’est utilisé quand on veut forcer le respect strict de la règle.   

📋 Effet : Audit
Résultat : Azure laisse passer la ressource, mais elle est signalée dans le rapport de conformité.
📌 Pratique pour observer sans bloquer.     
Tu ne veux pas bloquer les gens, mais tu veux savoir qui ne respecte pas la règle.     
Idéal pour surveiller sans empêcher les utilisateurs.     

➕ Effet : Append
Résultat : Azure ajoute automatiquement un paramètre manquant" avec une valeur prédéfinie (ex : "NonSpécifié").
📌 Utile pour enrichir les ressources sans les bloquer.

🔧 Effet : DeployIfNotExists
Résultat : Azure déclenche un déploiement correctif, par exemple un script qui ajoute un paramètre manquant.
📌 Utilisé quand on veut corriger automatiquement les non-conformités.

En résumé :    
Deny:	Bloque la création de ressources non conforme.
Audit:	Laisse passer mais signale seulement
Append:	corrige en ajoutant un paramètre dans la ressourceavec une valeur automatique
DeployIfNotExists: corrige en déployant une solution /déploie une action corrective 


Azure Policy ne fait pas qu’auditer. Elle peut bloquer, corriger ou enrichir les ressources selon l’effet choisi dans la règle.

📌 Exemples de politiques Azure :

| Policy      | Effet      |
|------------------|-----------------|
| Interdire (Bloquer) les déploiements de ressources hors de "France Central   |Empêcher les utilisateurs de créer des ressources ailleurs  |
| Imposer (obliger) Chiffrement obligatoire des disques des VM | Forcer le chiffrement des disques  |
| Forcer (Bloquer) un SKU spécifique pour les VMs (ex : taille D2s) |Contrôler les types autorisés)|
| Forcer (append) Vérifier la présence de tags |Ajouter automatiquement un tag à une ressource (ex : prod/dev/test)|
| Auditer l’usage d’un service obsolète |Génère des alertes sans bloquer|

   
**Initiative vs. Politique** ?
Politique = Une règle unique     
Initiative = Un groupe de plusieurs politiques (ex : tout un pack de règles sécurité pour les VM)→ utile pour appliquer un ensemble cohérent de règles.


2. **Role-Based Access Control (RBAC)**
Un outil pour gérer finement qui a accès à quelles ressources, et avec quel niveau de permissions.  

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
Tu veux surveiller et améliorer ton environnement avec des recommandations automatiques pour la sécurité, la performance, le coût. Quel service utilises-tu 
C'est un outils gratuit qui t’aide à  **surveiller et améliorer ton environnement Azure** avec des recommandantions pour:
🔒 Sécurité  Ex: Activer Azure Defender, corriger des ports ouverts   
⚙️ Haute disponibilité    Ex: Des ressources ne sont pas redondées	 => Ajouter des groupes de disponibilité pour les VMs critiques
⚡ Performance   Ex: Passer une base de données lente sur un niveau supérieur
💰 Coût   Ex: Supprimer des disques non utilisés, réduire la taille d’une VM pour économiser, stopper une VM inutilisée
🧰 Excellence opérationnelle   Ex: Mettre à jour les tags, organiser les ressources, planifier les sauvegardes



5. **Azure Blueprints**
Permet de déployer un ensemble complet de ressources + règles de gouvernance en un seul modèle.
Créer un modèle prêt à l’emploi avec règles + ressources
Tu veux standardiser le déploiement d’un environnement complet (réseau, VM, règles de sécurité, tags) pour chaque nouveau projet. 

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
Vous devez créer un environnement standardisé (avec un groupe de ressources, des rôles RBAC, et des stratégies).
Quelle solution utiliser ?
✅ Réponse attendue : Azure Blueprints, qui permet de déployer tous ces éléments de façon cohérente.


**Exemples concrets de gouvernance**
Tu veux :
Empêcher que des ressources soient supprimées accidentellement → Utilise Locks
Créer un environnement “prêt à l’emploi” pour ton équipe projet → Utilise Blueprints
Appliquer automatiquement les règles de sécurité et de conformité → Utilise Azure Policy
Limiter ce que chaque utilisateur peut faire dans Azure → Utilise RBAC
Améliorer la sécurité et les performances → Suis les conseils d’Azure Advisor


