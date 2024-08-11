# Vue.js App with Docker

Ce projet est une application Vue.js configurée pour être exécutée dans un conteneur Docker.

# Prérequis

- Docker
- Docker Compose

## **Cloner le dépôt**
```
git clone https://github.com/votre-utilisateur/vuejs-app.git
cd vuejs-app
```

## Construire l'image Docker
```
docker build -t vuejs-app .
```
## Exécution
Pour exécuter l'application dans un conteneur Docker :
```
docker run -it -p 8080:80 --rm --name vuejs-app-1 vuejs-app
```

## Développement

Pour un environnement de développement, vous pouvez monter le répertoire local dans le conteneur. Créez un fichier docker-compose.yml (optionnel) pour simplifier le processus :
```
version: '3'
services:
  vuejs-app:
    image: vuejs-app
    ports:
      - "8080:80"
    volumes:
      - .:/app
    command: npm run serve
```
Lancez les services avec Docker Compose :
```
docker-compose up
```