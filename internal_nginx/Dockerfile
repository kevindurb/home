FROM nginx:alpine

CMD mkdir -p /etc/nginx/conf.d/extra/
COPY ./*.conf /etc/nginx/conf.d/
COPY ./extra/*.conf /etc/nginx/conf.d/extra/
