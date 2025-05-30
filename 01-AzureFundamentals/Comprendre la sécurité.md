1. **Network Security Groups (NSG)**
Un NSG est un pare-feu de base au niveau réseau. Il permet de contrôler le trafic entrant et sortant des ressources Azure comme les machines virtuelles ou les sous-réseaux.

➤ Fonctionnement :
Il utilise des règles (inbound/outbound) pour autoriser ou bloquer des connexions selon :
Adresse IP source/destination
Port (ex. : 80 pour HTTP)
Protocole (TCP/UDP)

➤ Exemple :
Autoriser le trafic HTTP (port 80) depuis Internet vers une VM.
Bloquer tout autre trafic entrant.
Utilisation typique : Sécuriser les VM ou les sous-réseaux dans un VNet.
