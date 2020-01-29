Primeros pasos

1. Creamos nuestro Dockerfile
2. Añadimos el dockerfile y un .dockerignore conteniendo (node_modules, npm-debug.log) a la ruta principal de nuestra app
3. Conectamos nuestra base de datos de mongodb con nuestra node app : mongodb+srv://mongodb:mongodb@cluster0-btg13.mongodb.net/test?retryWrites=true&w=majority

FROM node:alpine3.10

# Ruta de la app
WORKDIR C:\Users\dmtroncoso\Desktop\mis-repositorios\express-mongoose\twheaterapp

# Instalamos las dependencias
# Copiamos los package.json generados de nuestra app
# disponible en la versión (npm@5+)
COPY package*.json ./

RUN npm install
# Si construimos el código para producción
# RUN npm ci --only=production

# App fuente Bundle
COPY . .

EXPOSE 8080
CMD [ "node", "./bin/www" ]

4. Construimos la imagen -> docker build -t tweatherapp/node-api-app .
5. Creamos e iniciamos nuestro contenedor -> docker run --name tweather-node-app -p 9001:3000 -d tweatherapp/node-api-app