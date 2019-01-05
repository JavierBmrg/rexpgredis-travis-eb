FROM node:alpine as production
WORKDIR "/app"
COPY ./package.json ./

RUN yarn install
COPY . .

CMD ["yarn", "start"]
