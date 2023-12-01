# Docker

> ❌ A travailler

> ✔️ Auto validation par l'étudiant

## 🎓 J'ai compris et je peux expliquer

- la création d'une image docker ✔️
- l'éxécution d'un container ✔️
- l'orchestration de containers avec docker-compose ✔️


## 💻 J'utilise

### Un exemple personnel commenté ✔️

Exemple de Dockerfile pour un backend.
Ce fichier Dockerfile est utilisé pour construire une image Docker pour une application Node.js TypeScript. 
- FROM node:18.18.2-alpine3.18: Cette instruction indique que l'image de base pour cette image Docker est basée sur Node.js version 18.18.2 et Alpine Linux version 3.18.
- WORKDIR /app: définit le répertoire de travail à /app. Cela signifie que les instructions suivantes seront exécutées dans ce répertoire.
- COPY package.json package.json: copie le fichier package.json depuis le répertoire de construction local vers le répertoire de travail /app dans l'image Docker.
- RUN npm i: exécute la commande npm i pour installer les dépendances.
- COPY src src: copie le répertoire src vers le répertoire de travail /app dans l'image Docker.
- COPY tsconfig.json tsconfig.json: Cette instruction copie le fichier tsconfig.json vers le répertoire de travail /app dans l'image Docker.
- CMD npm start: est la commande qui sera exécutée lorsque le conteneur basé sur cette image Docker sera lancé.
```
FROM node:18.18.2-alpine3.18

WORKDIR /app

COPY package.json package.json
RUN npm i

COPY src src
COPY tsconfig.json tsconfig.json

CMD npm start
```
Example de fichier docker-compose, ici pour un environnement de développement :
Ce fichier spécifie trois services (backend, db et frontend) ainsi que leur configuration.
Service backend:
- build: ./backend: Spécifie le chemin vers le répertoire contenant le Dockerfile pour construire l'image du service backend.
- ports: - 5000:5000: Mappe le port 5000 du conteneur sur le port 5000 de l'hôte.
- volumes: - ./backend/src:/app/src: Montre le répertoire ./backend/src du système hôte dans le répertoire /app/src du conteneur.
- env_file: ./backend/.env: Spécifie le fichier .env à utiliser pour charger les variables d'environnement du service backend.
  
Service db:
- image: postgres: Utilise l'image officielle PostgreSQL depuis Docker Hub.
- ports: - 5432:5432: Mappe le port 5432 du conteneur sur le port 5432 de l'hôte.
- volumes: - /var/lib/postgresql/data: Montre le volume de données de PostgreSQL sur le système hôte.
- env_file: .env: Spécifie le fichier .env à utiliser pour charger les variables d'environnement du service de base de données.

Service frontend:
- build: ./frontend: Spécifie le chemin vers le répertoire contenant le Dockerfile pour construire l'image du service frontend.
- command: npm run dev: Spécifie la commande à exécuter au lieu de la commande par défaut lors du démarrage du conteneur. Dans ce cas, il exécute npm run dev.
- ports: - 3000:3000: Mappe le port 3000 du conteneur sur le port 3000 de l'hôte.
- volumes: - ./frontend/src:/app/src: Montre le répertoire ./frontend/src du système hôte dans le répertoire /app/src du conteneur.
```
services:
  backend:
    build: ./backend
    ports:
      - 5000:5000
    volumes:
      - ./backend/src:/app/src
    env_file: ./backend/.env
  db:
    image: postgres
    ports:
     - 5432:5432
    volumes:
      - /var/lib/postgresql/data
    env_file: .env
  frontend:
    build: ./frontend
    command: npm run dev
    ports:
      - 3000:3000
    volumes:
      - ./frontend/src:/app/src
```

### Utilisation dans un projet ✔️

[https://github.com/LaureJanin/the-good-corner]

Description :

### Utilisation en production si applicable❌ / ✔️

[lien du projet](...)

Description :

### Utilisation en environement professionnel ❌ / ✔️

Description :

## 🌐 J'utilise des ressources

### Titre

- lien
- description

## 🚧 Je franchis les obstacles

### Point de blocage ❌ / ✔️

Description:

Plan d'action : (à valider par le formateur)

- action 1 ❌ / ✔️
- action 2 ❌ / ✔️
- ...

Résolution :

## 📽️ J'en fais la démonstration

- J'ai ecrit un [tutoriel](...) ❌ / ✔️
- J'ai fait une [présentation](...) ❌ / ✔️
