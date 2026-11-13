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
