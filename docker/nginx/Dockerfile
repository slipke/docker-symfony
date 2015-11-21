FROM nginx

RUN rm /etc/nginx/conf.d/default.conf
RUN echo "upstream php-upstream { server php:9000; }" > /etc/nginx/conf.d/upstream.conf

ADD symfony.conf /etc/nginx/conf.d/symfony.conf