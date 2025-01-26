
# 📌 DEVOIR N°1 - Module JEE : Développement Microservices avec Spring Cloud

## 📝 Description du projet 

Ce projet met en œuvre **une architecture microservices** en utilisant **Spring Cloud**. Il permet de gérer des **commandes** via des **opérations CRUD**, tout en intégrant des services de configuration centralisée, d’enregistrement, de supervision et de résilience.  

Il est divisé en **deux études de cas** :  
- **Étude de Cas 1** : Développement d’un microservice `microservice-commandes` avec **Spring Cloud Config** et **Spring Boot Actuator**.  
- **Étude de Cas 2** : Extension du projet avec l'ajout d’un **microservice-produit**, d’un **service d’enregistrement Eureka**, d’une **API Gateway**, et d’un mécanisme de **résilience avec Hystrix**.  

---

## 🔹 **Étude de Cas 1 : Microservice Commandes**  

### 🎯 **Objectif**  
Créer un microservice **"microservice-commandes"**, capable de réaliser des opérations CRUD sur l’entité **COMMANDE**, sans utiliser de base de données SQL.  

### 🏗️ **Structure de la table COMMANDE (Version 1)**  
| id  | description | quantité | date | montant |
|-----|------------|----------|------|---------|

### ⚙️ **Fonctionnalités**  
✅ **Configuration centralisée** : gestion de la configuration via **Spring Cloud Config** et **GitHub**.  
✅ **Propriété personnalisée** : `mes-config-ms.commandes-last`, permettant d'afficher les commandes reçues sur les *n* derniers jours.  
✅ **Chargement à chaud de la configuration** : modification de `mes-config-ms.commandes-last = 5` via **Spring Boot Actuator**, sans redémarrer l'application.  
✅ **Supervision de l’état du microservice** avec **Spring Boot Actuator** :  
   - Statut **"UP"** si des commandes sont disponibles.  
   - Statut **"DOWN"** si aucune commande n'est présente.  

---

## 🔹 **Étude de Cas 2 : Intégration d’Eureka, API Gateway et Résilience**  

### 🎯 **Objectif**  
Étendre le **microservice-commandes** en y ajoutant une gestion des **produits**, avec des services d’enregistrement et une API Gateway pour la communication entre microservices.  

### 🏗️ **Structure de la table COMMANDE (Version 2)**  
| id  | description | quantité | date | montant | id_produit |
|-----|------------|----------|------|---------|-----------|

### ⚙️ **Fonctionnalités**  
✅ **Enregistrement des microservices** (`microservice-commandes` et `microservice-produits`) dans **Eureka Server**.  
✅ **Implémentation d'une API Gateway** pour servir d’unique point d’accès aux microservices.  
✅ **Opérations CRUD** sur `microservice-commandes`.  
✅ **Simulation d’un timeout** et gestion de la **résilience avec Hystrix**, pour éviter les erreurs lors de la communication inter-microservices.  

---

## 👥 **Équipe de développement**  
👩‍💻 **Binôme** : *Mansour Lina* & *Houda El Bergui* - EMSI 3 5IIR 7 G1  

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

```
git clone https://github.com/linaman7/houda_lina_jee.git
cd houda_lina_jee
```

### ✅ **Tester la communication entre `microservice-commandes` et `ConfigServer`**  
1️⃣ **Connexion Internet requise**.  
2️⃣ Démarrer **ConfigServer** (`ConfigServer`).  
3️⃣ Lancer **microservice-commandes** (`microservice-commande`).  

### ✅ **Tester la communication entre `Eureka`, `API Gateway` et les microservices**  
1️⃣ Démarrer **Eureka Server** (`eureka-server`).  
2️⃣ Lancer **API Gateway** (`api-gateway`).  
3️⃣ Démarrer **microservice-commandes (Étude de Cas 2)** (`microservice-commande-etudeCas2`).  
4️⃣ Démarrer **microservice-produits (Étude de Cas 2)** (`microservice-produits-etudeCas2`).  

---

## 📸 **Captures d’écran**  

🖼️ **ConfigServer et microservice-commande**  
> Voici des captures d'écran illustrant cette communication :


