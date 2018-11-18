FROM alpine:3.8

RUN apk add --update \
    git \
    composer \
    php7 \
    php7-curl \
    cron \
  && rm -rf /var/cache/apk/*

RUN git clone https://github.com/peckrob/nest-watch /app && \
    cd /app/src && \
    composer install

RUN crontab -l | { cat; echo "*/5 * * * * /app/nestwatch"; } | crontab -

WORKDIR /app

CMD ["cron", "-f"]