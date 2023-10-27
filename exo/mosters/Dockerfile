FROM node:14 AS build
WORKDIR /app
COPY package.json package-lock.json /app/
RUN npm install --production

FROM node:14-alpine
WORKDIR /app
COPY --from=build /app/node_modules /app/node_modules
COPY . /app

EXPOSE 3000

ENV POSTER_DIR /app/movies

CMD ["node", "server.js"]