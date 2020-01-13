#Base Image
FROM node:alpine as appbuild

# Add files required to Image
WORKDIR '/app'

COPY package.json .

# Dependencies
RUN npm install

COPY . .
# build npm app
RUN npm run build

#Prod run image
FROM nginx
EXPOSE 80
COPY --from=appbuild /app/build /usr/share/nginx/html
