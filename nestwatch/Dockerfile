FROM alpine:3.8

RUN apk add --update \
    git \
    composer \
    php7 \
    php7-curl \
    curl \
  && rm -rf /var/cache/apk/*

RUN git clone https://github.com/peckrob/nest-watch /app && \
    cd /app/src && \
    composer install

RUN crontab -l | { cat; echo "*/1 * * * * /app/nestwatch -c /app/conf/nestwatch.conf"; } | crontab -

WORKDIR /app

CMD ["/usr/sbin/crond", "-f", "-d", "0"]