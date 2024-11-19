# 1. Introduction
Présentation du projet et des outils inclus dans l'architecture SOC : The Hive, Cortex, MISP, et Wazuh.
# 2. Pré-requis
## 2.1. Système d'exploitation
Ubuntu 22.04 .
![image](https://github.com/user-attachments/assets/c61886f2-f42b-4f1e-b902-b5b0fa231d8a)
## 2.2. Outils nécessaires
Docker et Docker Compose installés pour les services SOC.
Accès administrateur à la machine Ubuntu pour l'installation de Wazuh.
# 3. Installation des dépendances
## 3.1. Installation de Docker
Commandes pour installer Docker sur Ubuntu.
## 3.2. Installation de Docker Compose
Commandes pour installer Docker Compose version 3.7 ou plus récent.
# 4. Création des fichiers nécessaires
## 4.1. Configuration de Docker Compose
Contenu détaillé du fichier docker-compose.yml (voir la configuration ci-dessus).
## 4.2. Configuration des fichiers de The Hive et Cortex
Emplacement et contenu des fichiers de configuration nécessaires (exemple : application.conf).
# 5. Lancement des services
## 5.1. Commande de démarrage
Utilisation de la commande docker-compose up -d pour lancer les conteneurs.
## 5.2. Vérification de l'état des services
Commandes pour vérifier si tous les conteneurs sont démarrés correctement (docker ps).

