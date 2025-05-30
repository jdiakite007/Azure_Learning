 1. **Azure Monitor**
Un outil pour:
📦 Surveiller,
🛠️ Analyser
🚨 Alerter automatiquement
sur tout ce qui se passe dans tes ressources Azure ou On premise ou autre sclouds (comme les machines virtuelles, bases de données, applications web, etc.).
C’est comme un tableau de bord intelligent qui observe tout ce qui tourne dans Azure et te prévient quand quelque chose va mal (ex. : serveur trop lent, app qui plante, etc.).

🧰 Fonctionnalités principales :
📈 colletMetrics	=>                            Données chiffrées en temps réel (CPU, mémoire, latence...)
🪵 Logs (Azure Log Analytics)	 =>              Données plus détaillées (événements système, erreurs, etc.)
🔔 Alerts	 =>                                    Notifications automatiques selon certaines conditions
📊 Dashboards	   =>                                    Visualisation personnalisée des données
📤 Autoscale	     =>                     Ajuste automatiquement les ressources selon la charge

💡 Exemples :
Surveiller l'utilisation CPU d’une VM → alertes si dépasse 80%.
Analyser les erreurs HTTP d’une app web.
Déclencher un script ou envoyer un mail si une base SQL est en surcharge.

Azure Monitor sert à…	                                      Exemple
Voir comment vont tes ressources	                 "Ma VM est-elle trop chargée ?"
Recevoir des alertes	                               "Alerte si CPU > 85%"
Comprendre les problèmes	                      "Pourquoi mon app a planté ?"
Automatiser des actions	                            "Redémarrer le service si erreur critique"

2. **Azure Service Health**
c'est un service qui :
T’informe quand Azure a un problème (panne, alertes régionales)
T’avertit des maintenances prévues
T’aide à comprendre l’impact sur tes services => Intereruption de services possibles

🧰 Fonctionnalités clés 
🔧 Service Issues                     	Te dit s’il y a une panne Azure en cours
🛠️ Planned Maintenance	                    Te prévient en avance d’une opération prévue
📢 Health Advisories	                            Infos importantes à connaître (ex : mise à jour obligatoire bientôt, ou changements de service)
🔔 Alertes personnalisées	                       Tu peux recevoir un mail, Teams ou SMS si un service est affecté

💡 Exemples :
Une panne régionale d’Azure affecte votre app → vous êtes notifié.
Azure planifie une maintenance sur les bases de données → vous recevez un préavis.


 Exemple concret :
Tu as un site web hébergé dans France Central (Azure).
Un jour, ton app ne répond plus. Tu te connectes à Azure Service Health, et tu vois :
❗ Incident régional : Problème de réseau en France Central
🕒 Début de l’incident : 11h13 — Fin estimée : 12h30
📬 Impact : dégradations possibles sur les services App Service et Azure SQL


📌 En résumé simple :
Azure Service Health sert à…	Exemple
Être informé des problèmes Azure: exemple: 	Panne dans une région Azure
Préparer ton équipe à une coupure	: exemple Maintenance planifiée sur Azure SQL
Comprendre pourquoi ton service ralentit: exemple Incident réseau Azure
Être notifié dès que quelque chose arrive: exemple	Alerte sur incident affectant ton abonnement



