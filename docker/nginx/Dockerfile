FROM nginx

RUN rm /etc/nginx/conf.d/default.conf
RUN echo "upstream php-upstream { server php:9000; }" > /etc/nginx/conf.d/upstream.conf

ADD html.conf /etc/nginx/conf.d/html.conf
ADD symfony.custom /etc/nginx/conf.d/symfony.custom

#ADD server.key /etc/nginx/ssl/server.key
#ADD server.crt /etc/nginx/ssl/server.crt