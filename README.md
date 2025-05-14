# Projet Cloud : Déploiement sur Railway avec GitHub Actions

## Description
Ce projet est une application Node.js avec Express, connectée à une base de données PostgreSQL hébergée sur Railway. L'application expose deux routes :
- `/` : Affiche "Hello from Railway!".
- `/db` : Retourne l'heure actuelle depuis PostgreSQL.

Le déploiement est automatisé via GitHub Actions, qui installe les dépendances et déploie sur Railway à chaque push sur la branche `main`.

## Fonctionnalités
- Backend Node.js avec Express.
- Base de données PostgreSQL sur Railway.
- Déploiement continu avec GitHub Actions.

## Captures d'écran
- Tableau de bord Railway 
- Workflow GitHub Actions 
- Route `/` 
- Route `/db`

## Instructions de déploiement
1. Cloner le dépôt.
2. Configurer un projet Railway avec une base de données PostgreSQL.
3. Ajouter les variables `DATABASE_URL` et `PORT` sur Railway.
4. Configurer un token Railway dans les secrets GitHub (`RAILWAY_TOKEN`).
5. Pousser sur `main` pour déclencher le déploiement.
