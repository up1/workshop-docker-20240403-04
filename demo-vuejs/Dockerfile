FROM node:21-alpine3.18 as build
WORKDIR /app
COPY package*.json .
RUN npm i
COPY . .
RUN npm run build

FROM nginx:1.25.4
COPY --from=build /app/dist /usr/share/nginx/html