FROM alpine

RUN apk add --update \
    git \
    composer \
    php7 \
  && rm -rf /var/cache/apk/*

RUN git clone https://github.com/peckrob/nest-watch /app && \
    # chmod +x nestwatch && \
    cd /app/src && \
    composer install

WORKDIR /app

CMD ["/app/nestwatch"]