FROM node:18
WORKDIR /app

COPY package*.json ./

RUN npm ci

COPY . .
RUN npm run build
RUN mkdir /static
RUN cp -r build/* /static/

FROM nginx:1.22.1
COPY --from=0 /static /usr/share/nginx/html/

CMD ["npx", "-y", "http-server", "-p", "8000", "/app/build"]
