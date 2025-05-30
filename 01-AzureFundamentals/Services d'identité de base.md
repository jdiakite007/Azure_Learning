Azure propose des services pour :

Gérer les identités (utilisateurs, groupes, applications),
Contrôler les accès aux ressources,
Assurer la sécurité des connexions.

Principaux services :   
Service	                                                Rôle
Azure Active Directory (Azure AD)	               Service d'identité centralisé
Azure AD Multi-Factor Authentication (MFA)	            Ajout d'une étape de sécurité
Role-Based Access Control (RBAC)	                       Contrôle d’accès aux ressources
Azure AD B2B/B2C	                          Collaboration avec utilisateurs externes

**Différence entre Authentication et Authorization**
Authentification:	Vérifie qui vous êtes	              => Entrer nom d’utilisateur + mot de passe
Autorisation:	Définit ce que vous pouvez faire =>	Lire/écrire des fichiers dans un stockage

✅ Authentification = identité
✅ Autorisation = permissions


**Azure Active Directory (Azure AD)**
Azure AD est le service d'annuaire cloud de Microsoft. Il gère :
Utilisateurs
Groupes
Applications

Connexions sécurisées
➤ Fonctions principales :
Connexion à Microsoft 365, Azure Portal, applications tierces (Salesforce, Dropbox).
Authentification unique (SSO).
Gestion centralisée des comptes.
Intégration avec les annuaires locaux (AD on-premise) via Azure AD Connect.

➤ Exemple :
Un employé se connecte à son compte Microsoft 365 → Azure AD vérifie son identité et lui donne accès à ses outils de travail (Outlook, Teams, etc.).

**Azure Multi-Factor Authentication (MFA)**
Azure MFA ajoute une seconde couche de sécurité à la connexion, en plus du mot de passe.

➤ Types de vérification :
Code SMS
App mobile (Microsoft Authenticator)
Appel téléphonique

➤ Pourquoi l’utiliser ?
Les mots de passe peuvent être volés. MFA réduit fortement le risque de piratage.

➤ Exemple :
Étape 1 : L’utilisateur entre son mot de passe.
Étape 2 : Il reçoit un code sur son téléphone qu’il doit entrer pour valider la connexion.
💡 Très utile pour les accès sensibles comme l’administration Azure ou les données confidentielles.
