FROM node:alpine as production-build

WORKDIR '/app'
COPY package.json .
RUN yarn
COPY . .
RUN yarn build

FROM nginx
EXPOSE 3000
COPY ./nginx/default.conf /etc/nginx/conf.d/default.conf
COPY --from=production-build /app/build /usr/share/nginx/html
