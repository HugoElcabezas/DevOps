FROM node:16 AS build

WORKDIR /tmp/build

COPY . .

RUN npm i -g npm; npm i; npm run build

FROM nginx AS final

WORKDIR /usr/share/nginx/html

COPY --from=build /tmp/build/build .