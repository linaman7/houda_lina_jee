# DEVOIR N°1 - Module JEE : Développement Microservices avec Spring Cloud

## Description du projet

Ce projet consiste à développer deux versions d'un microservice de gestion des commandes avec Spring Cloud. Le microservice permet de réaliser des opérations CRUD sur une entité "COMMANDE", sans utiliser de base de données SQL.

## Étude de Cas 1
- **Objectif** : Développer un microservice "microservice-commandes" avec Spring Cloud, permettant de gérer les commandes à travers des opérations CRUD.
- **Fonctionnalités** :
  1. Gestion de la configuration via Spring Cloud et GitHub.
  2. Implémentation d'une propriété personnalisée pour afficher les commandes des derniers jours.
  3. Utilisation du service Actuator de Spring pour superviser la santé du microservice.
  4. Personnalisation de la supervision : le microservice est en "UP" lorsqu'il y a des commandes, sinon "DOWN".
  
## Étude de Cas 2
- **Objectif** : Ajouter un champ "id_produit" à la table "COMMANDE" et gérer les microservices "microservice-commandes" et "microservice-produit" via Eureka.
- **Fonctionnalités** :
  1. Enregistrement des microservices dans Eureka.
  2. Implémentation d'une API Gateway comme point d’accès unique.
  3. Implémentation des fonctionnalités CRUD pour "microservice-commandes".
  4. Simulation de timeout et protection des microservices avec Hystrix.
## Team de développement
- **Binôme** : Mansour Lina et Houda El Bergui, EMSI 3 5IIR 7 G1
- **Technologies utilisées** : Spring Cloud, Eureka, Actuator, Hystrix, API Gateway, Maven, GitHub.
