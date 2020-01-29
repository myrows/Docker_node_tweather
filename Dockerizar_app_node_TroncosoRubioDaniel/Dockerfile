FROM node:alpine3.10

# Ruta de la app
WORKDIR C:\Users\dmtroncoso\Desktop\mis-repositorios\express-mongoose\twheaterapp

# Instalar dependencias
# Se copia los archivos generados de la app de los package.json
# disponible para la versión (npm@5+)
COPY package*.json ./

RUN npm install
# Si lo estás construyendo como código de producción
# RUN npm ci --only=production

# Copiar apps principales Bundle
COPY . .

EXPOSE 8080
CMD [ "node", "./bin/www" ]