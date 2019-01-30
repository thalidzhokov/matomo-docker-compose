FROM nginx:latest

LABEL maintainer="Albert Thalidzhokov <thalidzhokov@gmail.com>"

ARG TERM=linux
ARG DEBIAN_FRONTEND=noninteractive

RUN apt-get update
RUN apt-get install -y apt-utils
RUN apt-get install -y \
    certbot \
    iputils-ping \
    mc \
    mlocate \
    nano

ADD nginx.conf /etc/nginx/
ADD default.conf /etc/nginx/conf.d/
ADD upstream.conf /etc/nginx/conf.d/

RUN mkdir -p /etc/nginx/ssl/example.net \
    && openssl req -x509 -nodes -newkey rsa:4096 \
        -keyout /etc/nginx/ssl/example.net/privkey.pem \
        -out /etc/nginx/ssl/example.net/fullchain.pem \
        -subj "/C=/ST=/L=/O=/CN=example.net" \
        && ln -sf /etc/nginx/ssl/example.net /etc/nginx/ssl/latest

RUN mkdir -p /var/www/certbot
ADD certbot.sh /etc/nginx/ssl/
RUN chmod +x /etc/nginx/ssl/certbot.sh

RUN usermod -u 1000 www-data

CMD ["nginx"]

EXPOSE 80 443