Apimocker en una imagen docker

Dockerfile para la generación de una imagen docker
Usage

FROM node:8
WORKDIR /api-clientes
RUN mkdir -p /api-clientes/node /api-clientes/node/mock/clientes
RUN chmod 777 -R /api-clientes
COPY /node/config-generated.json /api-clientes/node
COPY /node/mock/clientes/*.json /api-clientes/node/mock/clientes/
RUN npm install -g apimocker --unsafe-perm=true --allow-root
EXPOSE 8000
CMD ["apimocker", "-c", "/api-clientes/node/config-generated.json", "-p", "8000"]



Contactame

Déjeme un comentario si tienes algun problema en este repositorio de github o un DM en @Jovani_Aarzate mi cuenta de Twitter
