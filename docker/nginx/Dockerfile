FROM nginx

RUN set -xe;

RUN mkdir -p /data/nginx/cache

RUN echo "load_module /etc/nginx/modules/ngx_http_image_filter_module.so;\n$(cat /etc/nginx/nginx.conf)" > /etc/nginx/nginx.conf

RUN cat /etc/nginx/nginx.conf && nginx -t