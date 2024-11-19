# 1. Introduction
Présentation du projet et des outils inclus dans l'architecture SOC : The Hive, Cortex, MISP, et Wazuh.
# 2. Pré-requis
## 2.1. Système d'exploitation
Ubuntu 22.04 .

![image](https://github.com/user-attachments/assets/7b7e6b92-d884-4b9d-8df4-f08fac93c270)

## 2.2. Outils nécessaires
Docker et Docker Compose installés pour les services SOC.
Accès administrateur à la machine Ubuntu pour l'installation de Wazuh.

![image](https://github.com/user-attachments/assets/9891b488-93cb-498f-b825-9734787bc634)

# 3. Installation des dépendances

![image](https://github.com/user-attachments/assets/b5bdd3ae-1261-4f62-a8d5-971a2025459b)

# 4. Création des fichiers nécessaires
## 4.1. Configuration de Docker Compose
Contenu détaillé du fichier docker-compose.yml (voir la configuration ci-dessus).
## 4.2. Configuration des fichiers de The Hive et Cortex
Emplacement et contenu des fichiers de configuration nécessaires (exemple : application.conf).

![image](https://github.com/user-attachments/assets/d6d472f7-c174-44e1-808d-ea85bf166b65)

![image](https://github.com/user-attachments/assets/518e9dfb-1350-44c4-9319-19af0b38d3dd)


# 5. Lancement des services
## 5.1. Commande de démarrage
Utilisation de la commande docker-compose up -d pour lancer les conteneurs.

![image](https://github.com/user-attachments/assets/fa89a69f-b6eb-4f97-88a3-69aeca27ae6e)


## 5.2. Vérification de l'état des services
Commandes pour vérifier si tous les conteneurs sont démarrés correctement (docker ps).

![image](https://github.com/user-attachments/assets/dd4185d6-6f14-4993-b6dd-c96534d5901b)


