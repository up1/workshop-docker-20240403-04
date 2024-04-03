FROM node:21-alpine3.18 as build
WORKDIR /app
COPY . .
RUN npm i
RUN npm run build

FROM nginx:1.25.4
COPY --from=build /app/dist /usr/share/nginx/html