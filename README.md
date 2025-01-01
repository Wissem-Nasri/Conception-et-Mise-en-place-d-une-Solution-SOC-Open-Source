# 1. Introduction
Présentation du projet et des outils inclus dans l'architecture SOC : The Hive, Cortex, MISP, et Wazuh.
![Untitled Diagram (22)](https://github.com/user-attachments/assets/69a3b2ee-7272-418a-96fa-0b25739fb489)
# 2. Pré-requis
## 2.1. Système d'exploitation
Ubuntu 22.04 .

![image](https://github.com/user-attachments/assets/7b7e6b92-d884-4b9d-8df4-f08fac93c270)

## 2.2. Outils nécessaires
Docker et Docker Compose installés pour les services SOC.

Accès administrateur à la machine Ubuntu pour l'installation de Wazuh.

![image](https://github.com/user-attachments/assets/9891b488-93cb-498f-b825-9734787bc634)

# 3. Installation des dépendances
## 3.1. Installation de Docker

![image](https://github.com/user-attachments/assets/b5bdd3ae-1261-4f62-a8d5-971a2025459b)

## 3.2. Installation de Wazuh sur Ubuntu
### Préparation du système en mettant à jour les paquets avec apt update et apt upgrade.
sudo apt update && sudo apt upgrade
###  Installer curl .
sudo apt install curl
### Télécharger le script d'installation de Wazuh.
sudo curl -sO https://packages.wazuh.com/4.7/wazuh-install.sh
### Exécuter le script d'installation.
sudo bash ./wazuh-install.sh -a

#### verification de fonctionnemennt

![Capture d'écran 2024-11-19 152853](https://github.com/user-attachments/assets/ca35db49-5f77-4f48-9b93-600aab4f0e3c)

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

# 6. Intégration entre Cortex, MISP et The Hive
## 6.1. Intégration entre The Hive et Cortex
The Hive utilise Cortex comme moteur d’analyse pour automatiser les tâches et enrichir les alertes.
### Étape 1 : Récupération de la clé API Cortex
creation d'un organisation SOC 

![image](https://github.com/user-attachments/assets/fc42a4b8-ce8a-4ff4-8ade-d51a23748bc8)

Créez un utilisateur et Générez une clé API.

![image](https://github.com/user-attachments/assets/fbfd8653-c13b-4488-b5e4-a123b9e31803)

### Étape 2 : Configuration dans The Hive

![image](https://github.com/user-attachments/assets/3b820a35-d48e-476e-8fab-3292062f55eb)

## 6.2. Intégration entre The Hive et MISP
MISP fournit des données d’intelligence (indicateurs, menaces) que The Hive peut consommer pour enrichir les investigations.
### Étape 1 : Configuration de MISP dans The Hive
Générez une clé API MISP via Administration → Liste des utilisateurs → API Keys.

![image](https://github.com/user-attachments/assets/e334e1a1-532b-4339-9a9c-2943ed7ce1e4)

Ajoutez la configuration de MISP dans le fichier application.conf de The Hive :

![image](https://github.com/user-attachments/assets/507d9e70-2015-4356-907c-c232ecac7bbd)

integration effectué:

![image](https://github.com/user-attachments/assets/7bbb3874-8cca-4688-890c-778ee3ab55c3)

## 6.3 Configuration des Analyseurs MISP dans Cortex pour l'Organisation SOC

![image](https://github.com/user-attachments/assets/393530f6-008d-4074-898e-c4341c9add4f)

## 6.4 integration entre wazuh et the Hive
#### Création du script d'intégration personnalisé
Créez un script Python nommé custom-w2thive.py 

![image](https://github.com/user-attachments/assets/ce2ed194-9715-48d0-9556-cc8d23799e81)

Ce script contient une variable appelée lvl_threshold, définie par défaut à 0.
  Cela signifie que toutes les alertes générées par Wazuh seront envoyées à The Hive.
  Attention : Si vous surveillez de nombreux agents, cela pourrait générer un grand volume       d'alertes.
  Vous pouvez ajuster cette valeur pour ne transmettre que les alertes les plus critiques (le seuil va de 0 à 15, selon les classifications des règles Wazuh, disponibles dans le manuel).
#### Création d'un script Bash

![image](https://github.com/user-attachments/assets/760ec2bb-1b97-4466-88a8-25fb33d1b5ec)

Ce script servira à exécuter correctement le fichier Python custom-w2thive.py que vous avez créé.
#### Activation l'intégration dans la configuration de Wazuh

![image](https://github.com/user-attachments/assets/4f437e7c-199e-4514-a721-490dfa87499e)

![image](https://github.com/user-attachments/assets/e118aad2-4a60-4a24-96bc-ead9f59b16b3)

En résumé, cette procédure permet d'intégrer Wazuh et The Hive afin que les alertes de sécurité soient automatiquement transmises à The Hive pour une gestion centralisée.

# Projet terminé 🎉

Projet terminé 🎉
Le travail est désormais terminé ! 😊
Les traces de démonstration peuvent être consultées directement dans le rapport du projet. Restez à l'affût pour plus de détails !
