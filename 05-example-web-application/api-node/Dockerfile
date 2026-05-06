FROM node:19.6-alpine

WORKDIR /user/src/app

ENV NODE_ENV=production

COPY package*.json ./

RUN npm ci --only=production 

USER node

COPY --chown=node:node ./src .


EXPOSE 3000


CMD ["node" , "index.js"]