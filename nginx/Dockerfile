FROM nginx:1.22.1
COPY nginx.conf /etc/nginx/conf.d/default.conf
COPY --from=ekaterinakaiser/kittygram_frontend3:latest /usr/share/nginx/html/ /usr/share/nginx/html/
