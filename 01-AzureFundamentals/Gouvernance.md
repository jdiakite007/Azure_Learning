**Azure Governance – Gouvernance dans Azure**
Azure Governance – C’est quoi, en clair ?
c’est l’ensemble des règles et outils qui t’aident à organiser, sécuriser et contrôler ce que les gens peuvent faire dans Azure, pour que **tout reste cohérent** et **conforme aux règles de ton entreprise**.
Azure Governance, c’est comme une charte de bonne conduite + boîte à outils pour que ton cloud soit organisé, sécurisé, et contrôlé.

 **Les outils principaux de la gouvernance Azure :**

1. **Azure Policy** 
Définit des règles pour les actions autorisées, interdites ou obligatoires dans un environnement Azure.
📌 Exemples :
Interdire la création de ressources dans une région spécifique (ex : "East Asia").
Obliger le chiffrement des disques de toutes les VMs.
Vérifier que les tags "Environnement" soient appliqués à chaque ressource.

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

⚠️ Important pour la séparation des responsabilités

3. **Azure Locks (Verrous)**
ReadOnly : interdit la modification ou suppression
CanNotDelete : autorise la modification, interdit la suppression
🧠 Exemple :
Empêcher qu’un compte de stockage critique soit supprimé par erreur → appliquer un verrou CanNotDelete.

4. **Azure Advisor** – Assistant de recommandation
Azure Advisor analyse vos ressources et fournit des recommandations pour :Sécurité,Haute disponibilité,Performance, Cout
Excellence opérationnelle

📌 Exemple :
Advisor détecte une VM sous-utilisée → propose de la redimensionner pour économiser.


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


