#dockerfile:alpine_php_bebot
FROM alpine:latest
ENTRYPOINT ["/sbin/tini", "-g", "--"]
CMD ["/BeBot/docker-entrypoint.sh"]
RUN apk --no-cache --repository http://dl-3.alpinelinux.org/alpine/edge/community/ add \
    git php83-cli php83-phar php83-curl php83-sockets php83-pdo php83-pdo_mysql \
    php83-mbstring php83-ctype php83-bcmath php83-json php83-posix php83-simplexml \
    php83-dom php83-pcntl php83-zip php83-opcache php83-fileinfo php83-mysqli sudo tini
RUN git clone https://github.com/bitnykk/BeBot.git
COPY docker-entrypoint.sh /BeBot
RUN chmod +x /BeBot/docker-entrypoint.sh
RUN sudo ln -s /usr/bin/php83 /usr/bin/php
WORKDIR /BeBot