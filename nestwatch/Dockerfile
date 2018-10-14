FROM alpine

RUN apk add --update \
    git \
    composer \
    php7 \
    php7-curl \
  && rm -rf /var/cache/apk/*

RUN git clone https://github.com/peckrob/nest-watch /app && \
    cd /app/src && \
    composer install

WORKDIR /app

CMD ["/app/nestwatch"]