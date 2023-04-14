FROM node:19-bullseye-slim

WORKDIR /app
RUN npm install -g npm@latest

COPY ./package.json /app


#RUN chown -R node:node "/root/.npm"
#RUN chown -R node:node "/app"


RUN npm install && npm cache clean --force

ENV PATH ./node_modules/.bin/:$PATH
