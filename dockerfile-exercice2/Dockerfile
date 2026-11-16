
# Stage 1: Build the application
FROM node:22.23.5-alpine3.24 AS builder

WORKDIR /app

COPY package.json package-lock.json ./

RUN npm ci

COPY . .

RUN npm run build

# Stage 2: Run the application
FROM nginxinc/nginx-unprivileged:1.31.7-alpine3.24 AS production

COPY --from=builder --chown=101:101 /app/dist/ /usr/share/nginx/html/

USER 101

EXPOSE 8080
