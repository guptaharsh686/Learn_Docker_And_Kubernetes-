FROM node:latest as build
WORKDIR /usr/local/app

COPY ./ /usr/local/app/

RUN npm install

# when we do build we get all app related compiled files in dist folder
RUN npm run build


FROM nginx:latest

# copy compiled files to nginx to serve
COPY --from=build /usr/local/app/dist/learn-docker-app /usr/share/nginx/html

#EXPOSE 80