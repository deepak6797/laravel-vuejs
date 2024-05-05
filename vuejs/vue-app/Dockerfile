# Build Stage

FROM node:16.10.0-alpine3.13 as build-stage

WORKDIR /app

COPY ./src/package*.json ./

RUN npm install

COPY ./src .

RUN npm run build

FROM nginx:stable-alpine as production-stage

COPY --from=build-stage /app/dist /usr/share/nginx/html

COPY ./site.conf /etc/nginx/conf.d/default.conf

EXPOSE 80

CMD ["nginx", "-g", "daemon off;"]