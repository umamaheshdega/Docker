# FROM nginx
FROM nginx:stable-alpine3.20-perl
RUN rm -rf /usr/share/nginx/html/index.html && \
    rm -rf /etc/nginx/nginx.conf && \
    rm -rf /etc/nginx/conf.d/default.conf && \
    mkdir -p /var/cache/nginx/client_temp /var/cache/nginx/proxy_temp \
             /var/cache/nginx/fastcgi_temp /var/cache/nginx/uwsgi_temp \
             /var/cache/nginx/scgi_temp && \
    chown -R nginx:nginx /var/cache/nginx && \
    chown -R nginx:nginx /etc/nginx/ && \
    chmod -R 755 /etc/nginx/ && \
    chown -R nginx:nginx /var/log/nginx 
COPY nginx.conf /etc/nginx/nginx.conf 
COPY code /usr/share/nginx/html/
USER nginx