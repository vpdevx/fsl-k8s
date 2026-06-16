FROM node:15 as builder

WORKDIR /app

COPY . .

RUN npm install

RUN  npm run build

FROM nginx:alpine

WORKDIR /usr/share/nginx/html

COPY --from=builder /app/build .

EXPOSE 80

ENTRYPOINT ["nginx", "-g", "daemon off;"]