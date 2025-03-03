FROM node:18 as builder
WORKDIR /app

COPY package*.json ./

RUN npm ci

COPY . .
RUN npm run build

FROM nginx:1.22.1
COPY --from=builder /app/build /usr/share/nginx/html/
