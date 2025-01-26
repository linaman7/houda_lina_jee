
## 📌 **Devoir N°1 - Module JEE : Développement Microservices avec Spring Cloud**

### 📝 **Description du projet**

Ce projet met en œuvre une architecture basée sur des **microservices** avec **Spring Cloud**, permettant de gérer les commandes via des opérations **CRUD** tout en intégrant plusieurs services essentiels, tels que la **configuration centralisée**, l'**enregistrement des microservices**, la **supervision** et la **résilience**.

Le projet se divise en **deux études de cas** principales :

- 🟢 **Étude de Cas 1** : Développement du microservice `microservice-commandes` avec **Spring Cloud Config** et **Spring Boot Actuator**.
- 🔵 **Étude de Cas 2** : Ajout du `microservice-produits`, d’un **Eureka Server**, d’une **API Gateway**, et implémentation de la **résilience** avec **Hystrix**.

---

### 🔹 **Étude de Cas 1 : Microservice Commandes**

#### 🎯 **Objectif**
Développer un **microservice-commandes** permettant d’effectuer des opérations CRUD sur l’entité **COMMANDE**, sans utiliser de base de données SQL.

#### 🏗️ **Structure de la table COMMANDE (Version 1)**

| id  | description | quantité | date       | montant |
| --- | ----------- | -------- | ---------- | ------- |
| 1   | ...         | ...      | ...        | ...     |

#### ⚙️ **Fonctionnalités**
- ✅ **Configuration centralisée** via **Spring Cloud Config** et **GitHub**.
- ✅ Propriété personnalisée : `mes-config-ms.commandes-last`, permettant d’afficher les commandes des 5 derniers jours.
- ✅ **Chargement à chaud de la configuration** avec **Spring Boot Actuator** : mise à jour de `mes-config-ms.commandes-last` sans redémarrage de l'application.
- ✅ **Supervision** du microservice avec **Spring Boot Actuator** :
  - Statut **UP** si des commandes existent.
  - Statut **DOWN** si aucune commande n’est enregistrée.

---

### 🔹 **Étude de Cas 2 : Intégration d’Eureka, API Gateway et Résilience**

#### 🎯 **Objectif**
Étendre le **microservice-commandes** pour inclure la gestion des produits, les services d’enregistrement et une **API Gateway** pour faciliter la communication entre les microservices.

#### 🏗️ **Structure de la table COMMANDE (Version 2)**

| id  | description | quantité | date       | montant | id_produit |
| --- | ----------- | -------- | ---------- | ------- | ---------- |
| 1   | ...         | ...      | ...        | ...     | ...        |

#### ⚙️ **Fonctionnalités**
- ✅ Enregistrement des microservices (`microservice-commandes` et `microservice-produits`) dans **Eureka Server**.
- ✅ Mise en place d’une **API Gateway** comme point d’entrée unique aux microservices.
- ✅ Opérations **CRUD** complètes sur `microservice-commandes`.
- ✅ Simulation de **timeout** et gestion de la résilience avec **Hystrix** pour sécuriser la communication inter-microservices.

---

### 👥 **Équipe de développement**

- 👩‍💻 **Binôme** : Mansour Lina & Houda El Bergui - EMSI 5IIR 7 G1

---

### 🛠️ **Technologies utilisées**
- **Spring Cloud** (Config Server, Eureka, API Gateway)
- **Spring Boot Actuator**
- **Hystrix**
- **Maven**
- **GitHub**

---

### 🚀 **Installation et exécution**

1. **Cloner le projet**  
   Dépôt GitHub : [GitHub Repository](https://github.com/linaman7/houda_lina_jee.git)
   ```bash
   git clone https://github.com/linaman7/houda_lina_jee.git
   cd houda_lina_jee
   ```

2. **Tester la communication entre `microservice-commandes` et `ConfigServer`**
   - Connexion Internet requise.
   - Démarrer **ConfigServer**.
   - Lancer **microservice-commandes**.

3. **Tester la communication entre Eureka, API Gateway et les microservices**
   - Démarrer **Eureka Server**.
   - Lancer **API Gateway**.
   - Démarrer `microservice-commandes` (Étude de Cas 2).
   - Démarrer `microservice-produits` (Étude de Cas 2).

---

### 🖼️ **Captures d’écran**

Les captures d’écran des résultats de l’action `getRecentCommandes` du **microservice-commande** et des états des microservices dans **Eureka Server**, **API Gateway**, et autres composants sont disponibles dans un **fichier séparé des captures d’écran**.


### 📜 **Livrables**
- 📌 **Code source** : Déposé sur GitHub ([Lien du repo](https://github.com/linaman7/houda_lina_jee.git)).
- 📌 **Captures d’écran** : **Consulter le fichier séparé des captures d’écran**.

