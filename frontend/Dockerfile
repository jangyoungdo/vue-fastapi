FROM node:16 AS build

WORKDIR /app 

ADD package*.json .

RUN npm install 

ADD . .

RUN npm run build

FROM nginx:alpine

COPY --from=build /app/dist /usr/share/nginx/html
COPY --from=build /app/default.conf /app/default.conf /etc/nginx/conf.d/default.conf


