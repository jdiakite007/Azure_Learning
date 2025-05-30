1. **Qu’est-ce qu’un SLA (Service Level Agreement)**?     
Un SLA, ou Contrat de niveau de service, est une garantie écrite de Microsoft sur la disponibilité (uptime) d’un service Azure.    
Il indique la durée maximale de panne autorisée (en pourcentage de temps) , sinon vous pouvez demander un remboursement partiel (crédit).   

📌 Exemple :     
Un SLA de 99,9 % signifie que le service peut être indisponible (panne) pendant 8h45 max par an.

🧮 2. Exemples de niveaux de SLA
SLA Azure	                                     Temps d’indisponibilité max par mois
99 %	                                              ~ 7 heures
99,9 % (Three 9s)	                                  ~ 43 minutes
99,99 % (Four 9s)	                                    ~ 4 minutes

📘 Plus le pourcentage est élevé, plus la disponibilité est élevée, et donc plus le service est fiable.    

🔗 **Qu’est-ce qu’un SLA composite (Composite SLA)?** 
Si ton application dépend de plusieurs services en même temps, le SLA global est calculé en multipliant les SLA de chaque service :    

✏️ Exercice pratique de calcul SLA
💼 Contexte :
Tu crées une application web sur Azure avec 3 composants :

Composant	SLA officiel Azure
Azure App Service	99.95 %
Azure SQL Database	99.99 %
Azure Storage Account	99.9 %

❓Quel est le SLA composite de l'application ?
✅ Solution :
SLA global = 0.9995 × 0.9999 × 0.999 = 0.9984 ≈ 99.84 %
➡️ SLA final : 99,84 %

⚠️ Si l’un des services tombe, ton application peut ne plus fonctionner. C’est pourquoi on multiplie les SLA.

📌 Définitions clés :      
SLA (Service Level Agreement)  = Promesse ou garantie disponibilité d’un service Azure (en %) ou Temps d’indisponibilité ou	
SLA individuel =	SLA spécifique à un service (ex : Azure SQL = 99,99 %)
SLA global / composite	Calculé si plusieurs services sont utilisés ensemble → Produit des SLAs
Plus le SLA est élevé, plus le service est fiable, mais souvent plus coûteux.

📊 Temps d’indisponibilité selon SLA (par mois)
SLA (%)	              Temps d'arrêt autorisé (par mois)
99.0 %	                 ~7 h 18 min
99.9 %	                  ~43 min
99.95 %	                     ~21 min
99.99 %	                    ~4 min
100 %	                         0 min
Tu peux améliorer le SLA global en répliquant ou en utilisant des services haute disponibilité.


