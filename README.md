# Activité Pratique N°1 – Event Driven Architecture avec Kafka

---

## Introduction

Cette activité pratique a pour objectif de mettre en œuvre une **architecture pilotée par les événements (Event Driven Architecture)** en utilisant **Apache Kafka** et **Spring Cloud Stream**.

L'objectif principal est de comprendre le fonctionnement d'un système distribué basé sur des flux de messages asynchrones, ainsi que d'explorer les concepts de **Producer**, **Consumer**, **Supplier** et **Stream Processing** au sein d'un écosystème Kafka.  
Le tout est déployé dans un environnement **Docker** afin de faciliter la configuration et l'exécution des différents services.

---

## I. Mise en place de l'environnement Kafka avec Docker

### 1. Création du fichier `docker-compose.yml`
   - **Zookeeper**
   - **Kafka Broker**

### 2. Démarrage des conteneurs Docker

    docker-compose up -d

### 3. Tests avec Kafka-console-producer et kafka-console-consumer

- **Kafka Console Producer**
- **Kafka Console Consumer**

Ces tests ont permis de valider la communication entre les différents composants Kafka.

---

## II. Implémentation des microservices Kafka avec Spring Boot et Spring Cloud Stream
Cette partie consiste à développer plusieurs microservices communiquant entre eux via Kafka.

### 1. Service Producer KAFKA via un Rest Controler
- **Implémentation d'un Producteur Kafka exposé via un RestController.**
- **Ce service permet d'envoyer des messages dans un topic Kafka défini.**
- **Exemple d'appel REST :**

    ```bash
    POST /publish?message=HelloKafka

### 2. Service Consumer KAFKA
- Implémentation d'un Consumer Kafka recevant les messages produits par le Producer.
- Le Consumer consomme les messages du topic et les affiche dans la console ou les traite selon la logique métier.

### 3. Service Supplier KAFKA
- Implémentation d'un Supplier Kafka, permettant la génération automatique et périodique de messages dans un topic.
- Ce service agit comme une source continue de données.

### 4. Service de Data Analytics Real Time Stream Processing avec Kaflka Streams
- Utilisation de Kafka Streams pour effectuer un traitement analytique en temps réel des données transitant dans les topics.
- Exemple d'opération : agrégation, filtrage ou comptage des occurrences de messages.
- Le résultat du flux est publié dans un nouveau topic pour être consommé par l'application Web.

### 5. Application Web temps réel
- Développement d'une petite application Web affichant en temps réel les résultats du traitement de flux.
- Connexion à Kafka pour recevoir les données du Stream Processing et les visualiser dynamiquement (ex. statistiques, graphiques, logs temps réel, etc.).

## III. Concepts Clés Abordés
- Architecture pilotée par les événements (Event Driven Architecture)
- Messagerie asynchrone et découplage entre producteurs et consommateurs
- Spring Cloud Stream et le concept de bindings (input / output)
- Kafka Streams API pour le traitement temps réel des données
- Utilisation de Docker pour la conteneurisation et la gestion simplifiée des services distribués

---

## Conclusion
Cette activité pratique a permis de mettre en œuvre concrètement les principes d'une architecture événementielle distribuée.
Grâce à Kafka et Spring Cloud Stream, il a été possible d'établir un flux complet de production, consommation et traitement de données en temps réel.

L'approche par événements favorise la scalabilité, la résilience et le découplage des services, illustrant parfaitement les fondements des systèmes distribués modernes.

---

## Réalisé par :
- **Nom :** Wendbénédo Albéric Darius KONSEBO
- **Module :** Systèmes Distribués et Parallèles
- **Encadré par :** Pr. Mohamed YOUSSFI
- **Année académique :** 2025 - 2026