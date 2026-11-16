# Objectif

**Mettre en place une application multi-conteneurs utilisant Drupal comme serveur web et PostgreSQL comme base de données, à l'aide de Docker Compose.**

## Réalisation

Un fichier docker-compose.yml a été créé avec deux services :

Drupal : image drupal:10-apache, accessible sur le port 8081 de l'hôte.

PostgreSQL : image postgres:16, utilisée pour stocker les données de Drupal.

Une variable d'environnement POSTGRES_PASSWORD a été configurée pour définir le mot de passe de la base de données.

Des volumes Docker ont également été utilisés pour conserver les fichiers Drupal et les données PostgreSQL.

## Commandes utilisées

docker compose config --quiet : vérifier la configuration du fichier Compose.

docker compose up -d : créer et démarrer les conteneurs.

docker compose ps : vérifier l'état des services.

docker compose down : arrêter et supprimer les conteneurs.

docker compose up -d : redémarrer les services.

## Configuration de la base de données

Dans l'assistant d'installation de Drupal, la connexion PostgreSQL a été configurée avec le nom du service postgres comme hôte de la base de données, et le port 5432.

Cela permet aux deux conteneurs de communiquer grâce au réseau créé automatiquement par Docker Compose.

## Vérification de la persistance

Après l'installation de Drupal, les conteneurs ont été arrêtés avec docker compose down, puis recréés avec docker compose up -d.

Résultat : Le site Drupal est resté fonctionnel et les données de configuration ont été conservées.

Cela démontre que les volumes Docker permettent de conserver les données indépendamment du cycle de vie des conteneurs.

## Conclusion

L'exercice a permis de mettre en place une application multi-conteneurs avec Docker Compose, de configurer la communication entre Drupal et PostgreSQL et de vérifier la persistance des données grâce aux volumes Docker.