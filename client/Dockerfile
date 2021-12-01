FROM node:16-alpine as builder
WORKDIR '/app'
COPY ./package.json ./
RUN npm install
COPY . .
RUN npm run build

from nginx
expose 3000
copy ./nginx/default.conf /etc/nginx/conf.d/default.conf
copy --from=builder /app/build /usr/share/nginx/html
