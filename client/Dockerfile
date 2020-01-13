#Base Image
FROM node:alpine as builder

# Set working dir context 
WORKDIR '/app'

# Add files required to Image
COPY ./package.json ./

# Dependencies
RUN npm install

COPY . .
# build npm app
RUN npm run build

#Prod run image
FROM nginx
EXPOSE 3000
COPY ./nginx/default.conf /etc/nginx/conf.d/default.conf 
COPY --from=builder /app/build /usr/share/nginx/html
