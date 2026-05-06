FROM node:19.6-alpine

WORKDIR /user/src/app

COPY package*.json ./

RUN npm install 

COPY . .


CMD ["npm", "run", "dev"]