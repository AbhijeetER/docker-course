FROM node:19.4-bullseye AS build
WORKDIR /user/src/app

COPY package*.json ./

RUN --mount=type=cache,target=user/src/app/.npm \ 
npm set cache /user/src/app/.npm && \
npm ci


COPY . .

RUN npm run build
###

FROM nginx:1.22-alpine

COPY nginx.conf /etc/nginx/conf.d/default.conf

COPY --from=build user/src/app/dist/ /user/share/nginx/html

EXPOSE 80