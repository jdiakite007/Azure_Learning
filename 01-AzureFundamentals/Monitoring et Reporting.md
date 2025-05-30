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
Azure Service Health vous informe de l’état des services Azure que vous utilisez : pannes, maintenance planifiée, alertes régionales.
Etre informé des interruptions Azure
🧰 Fonctionnalités principales :
🔕 Service Issues	        =>                     Incidents impactant vos services Azure
🛠️ Planned Maintenance	  =>                     Maintenances prévues qui pourraient affecter vos services
📢 Health Advisories	      =>                 Informations importantes sur l’état ou changements de service
🔔 Alertes personnalisées     =>                  	Recevoir des alertes par mail, webhook ou Teams

💡 Exemples :
Une panne régionale d’Azure affecte votre app → vous êtes notifié.
Azure planifie une maintenance sur les bases de données → vous recevez un préavis.




