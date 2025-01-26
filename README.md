
# 📌 **DEVOIR N°1 - Module JEE : Développement Microservices avec Spring Cloud**  

## 📝 **Description du projet**  

Ce projet met en œuvre **une architecture microservices** avec **Spring Cloud**, permettant la gestion de **commandes** via des **opérations CRUD**, tout en intégrant des services de **configuration centralisée**, **enregistrement des microservices**, **supervision** et **résilience**.  

Le projet est divisé en **deux études de cas** :  
- 🟢 **Étude de Cas 1** : Développement du microservice `microservice-commandes` avec **Spring Cloud Config** et **Spring Boot Actuator**.  
- 🔵 **Étude de Cas 2** : Ajout du **microservice-produits**, d’un **Eureka Server**, d’une **API Gateway**, et implémentation de la **résilience avec Hystrix**.  

---

## 🔹 **Étude de Cas 1 : Microservice Commandes**  

### 🎯 **Objectif**  
Développer un **microservice-commandes** permettant d'effectuer des **opérations CRUD** sur l’entité **COMMANDE**, sans base de données SQL.  

### 🏗️ **Structure de la table COMMANDE (Version 1)**  
| id  | description | quantité | date | montant |
|-----|------------|----------|------|---------|

### ⚙️ **Fonctionnalités**  
✅ **Configuration centralisée** via **Spring Cloud Config** et **GitHub**.  
✅ **Propriété personnalisée** : `mes-config-ms.commandes-last` permettant d'afficher les commandes des *5* derniers jours.  
✅ **Chargement à chaud de la configuration** avec **Spring Boot Actuator** : mise à jour de `mes-config-ms.commandes-last` sans redémarrer l'application.  
✅ **Supervision du microservice** avec **Spring Boot Actuator** :  
   - Statut **UP** si des commandes existent.  
   - Statut **DOWN** si aucune commande n'est enregistrée.  

---

## 🔹 **Étude de Cas 2 : Intégration d’Eureka, API Gateway et Résilience**  

### 🎯 **Objectif**  
Étendre le **microservice-commandes** avec une gestion des **produits**, des services d’enregistrement et une API Gateway pour la communication entre microservices.  

### 🏗️ **Structure de la table COMMANDE (Version 2)**  
| id  | description | quantité | date | montant | id_produit |
|-----|------------|----------|------|---------|-----------|

### ⚙️ **Fonctionnalités**  
✅ **Enregistrement des microservices** (`microservice-commandes` et `microservice-produits`) dans **Eureka Server**.  
✅ **Mise en place d'une API Gateway** comme unique point d’accès aux microservices.  
✅ **Opérations CRUD** complètes sur `microservice-commandes`.  
✅ **Simulation d’un timeout** et gestion de la **résilience avec Hystrix** pour sécuriser la communication inter-microservices.  

---

## 👥 **Équipe de développement**  
👩‍💻 **Binôme** : *Mansour Lina* & *Houda El Bergui* - EMSI 5IIR 7 G1  

### 🛠️ **Technologies utilisées**  
🔹 **Spring Cloud** (Config Server, Eureka, API Gateway)  
🔹 **Spring Boot Actuator**  
🔹 **Hystrix**  
🔹 **Maven**  
🔹 **GitHub**  

---

## 🚀 **Installation et exécution**  

### ✅ **Cloner le projet**  
📂 **Dépôt GitHub** : [GitHub Repository](https://github.com/linaman7/houda_lina_jee.git)  

```sh
git clone https://github.com/linaman7/houda_lina_jee.git
cd houda_lina_jee
```

### ✅ **Tester la communication entre `microservice-commandes` et `ConfigServer`**  
1️⃣ **Connexion Internet requise**  
2️⃣ Démarrer **ConfigServer** (`ConfigServer`)  
3️⃣ Lancer **microservice-commandes** (`microservice-commande`)  

### ✅ **Tester la communication entre `Eureka`, `API Gateway` et les microservices**  
1️⃣ Démarrer **Eureka Server** (`eureka-server`)  
2️⃣ Lancer **API Gateway** (`api-gateway`)  
3️⃣ Démarrer **microservice-commandes (Étude de Cas 2)** (`microservice-commande-etudeCas2`)  
4️⃣ Démarrer **microservice-produits (Étude de Cas 2)** (`microservice-produits-etudeCas2`)  

---

## 📸 **Captures d’écran**  

### 🖼️ **ConfigServer et microservice-commandes**  
📌 **Configuration récupérée depuis GitHub** 
![image alt](https://raw.githubusercontent.com/linaman7/houda_lina_jee/main/le%20parametre%20%C3%A0%20r%C3%A9cup%C3%A9rer%20par%20le%20ConfigServer%20dans%20github..png)




### 🖼️ **Eureka, API Gateway et Produit et Commandes**  
Pour bien lancer l'application il faut d'abord lancer le EurekaServer puis api-gateway et finalement les deux microservices
![Résultat de l'action getRecentCommandes de microservice-commande](images/les ports.png)



On peut bien apercevoir que notre endpoint est activé via l'api gateway

Maintenant essayons de passer par l api gateway vers commande vers produit il faut qu' on atteint cette endpoint du controlleur du microservice commande qui va communiquer avec le microservice produit


## 📜 **Livrables**  
📌 **Code source** : Déposé sur GitHub ([Lien du repo](https://github.com/linaman7/houda_lina_jee.git))  
📌 **Démonstration** : Présentation du fonctionnement des microservices  
📌 **Captures d’écran** : Illustrations du bon fonctionnement du projet  

---

🎯 **Ce README est maintenant structuré, lisible et bien organisé !** Dis-moi si tu veux ajouter ou modifier quelque chose. 😊🚀
