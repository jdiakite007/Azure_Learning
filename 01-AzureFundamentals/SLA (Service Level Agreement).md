1. **Qu’est-ce qu’un SLA (Service Level Agreement)**?
Un SLA, ou Contrat de niveau de service, est une garantie écrite de Microsoft sur la disponibilité (uptime) d’un service Azure.

👉 Il indique le pourcentage de temps où le service doit être disponible, sinon vous pouvez demander un remboursement partiel (crédit).

📌 Exemple :
Un SLA de 99,9 % signifie que le service peut être indisponible pendant 8h45 max par an.

🧮 2. Exemples de niveaux de SLA
SLA Azure	                                     Temps d’indisponibilité max par mois
99 %	                                              ~ 7 heures
99,9 % (Three 9s)	                                  ~ 43 minutes
99,99 % (Four 9s)	                                    ~ 4 minutes

📘 Plus le pourcentage est élevé, plus la disponibilité est élevée, et donc plus le service est fiable.

🔗 3. Qu’est-ce qu’un SLA composite (Composite SLA) 
Si ton application dépend de plusieurs services en même temps, le SLA global est calculé en multipliant les SLA de chaque service :

✏️ Exemple :
Azure Web App SLA = 99,95 %    et  Azure SQL Database SLA = 99,99 %

👉 Ton application dépend des deux, donc la disponibilité globale est :
SLA global = 99,95 % × 99,99 % ≈ 99,94 %

⚠️ Si l’un des services tombe, ton application peut ne plus fonctionner. C’est pourquoi on multiplie les SLA.




✅ 4. Comment choisir un SLA adapté à votre application ?
Posez-vous ces questions :

Question	Explication
❓ Quelle est l’importance de mon application ?	Critique ? Disponible 24/7 ?
❓ Quelle interruption est acceptable ?	Quelques minutes ? Jamais ? Pendant la nuit uniquement ?
❓ Est-ce que j’ai une solution de secours ?	Redondance, sauvegarde, réplication multi-région ?

🎯 Objectif :
Appli critique = besoin d’un SLA élevé (99,99 %+)
Appli interne ou non critique = SLA moyen (99,9 %)
Et si vous voulez une tolérance aux pannes élevée, pensez à répliquer votre solution sur plusieurs zones/régions.


✅ Fiche pratique SLA (AZ-900)
📌 Définitions clés :
Terme	Signification
SLA (Service Level Agreement)	Garantie de disponibilité d’un service Azure (en %)
SLA individuel	SLA spécifique à un service (ex : Azure SQL = 99,99 %)
SLA global / composite	Calculé si plusieurs services sont utilisés ensemble → Produit des SLAs
Temps d’indisponibilité max	Durée maximale de panne autorisée selon le SLA

📊 Temps d’indisponibilité selon SLA (par mois)
SLA (%)	Temps d'arrêt autorisé (par mois)
99.0 %	~7 h 18 min
99.9 %	~43 min
99.95 %	~21 min
99.99 %	~4 min
100 %	0 min

🧮 Formule du SLA composite :
csharp
Copier
Modifier
SLA global = SLA Service 1 × SLA Service 2 × ... × SLA Service n
🧠 Cette méthode est utilisée si les services dépendent les uns des autres (ex : web app + base de données).

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

🟡 Ce SLA signifie que ton app pourrait être indisponible pendant environ 1h10 par mois, ce qui est important à savoir pour les apps critiques.

🎓 À retenir pour l’examen AZ-900 :
Un SLA est une promesse de disponibilité.
Un SLA composite est calculé en multipliant les SLAs des services interdépendants.
Plus le SLA est élevé, plus le service est fiable, mais souvent plus coûteux.
Tu peux améliorer le SLA global en répliquant ou en utilisant des services haute disponibilité.
