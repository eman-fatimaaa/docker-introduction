# Utiliser une image de base Node.js légère

# Définir le répertoire de travail de l'application

# Copier les fichiers package.json et package-lock.json pour installer les dépendances

# Copier les fichiers sources de l'application dans le conteneur

# Installer les dépendances, construire l'application et nettoyer les modules Node.js

# Exposer le port

# Démarrer l'application 

FROM node:18-alpine

WORKDIR app

COPY package.json package-lock.json ./

RUN npm install

COPY src ./src
COPY public ./public

RUN npm install -g serve
RUN npm run build
RUN rm -fr node_modules

EXPOSE 3000

CMD ["serve", "-s", "build"]
