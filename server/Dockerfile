#Base Image
FROM node:alpine

# Add files required to Image
WORKDIR '/app'

COPY package.json ./

# Depenencies
RUN npm install

COPY . .
# Startup
CMD ["npm", "run", "start"]
