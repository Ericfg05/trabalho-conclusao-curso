FROM nginx:latest

RUN groupadd -g 1000 user-teste && \
    useradd -u 1000 -g user-teste user-teste

COPY ./nginx.conf /etc/nginx/
COPY ./index.html /usr/share/nginx/html

RUN mkdir -p /var/cache/nginx/client_temp \
    && chown -R user-teste:user-teste /var/cache/nginx \
    && chown -R user-teste:user-teste /usr/share/nginx/html \
    && chown -R user-teste:user-teste /etc/nginx 
USER user-teste 

EXPOSE 80
