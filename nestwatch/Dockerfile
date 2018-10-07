FROM alpine

RUN apk add --update \
    git \
  && rm -rf /var/cache/apk/*

RUN git clone https://github.com/peckrob/nest-watch /app && \
    chmod +x nestwatch && \
    cd src && \
    composer install

WORKDIR /app

CMD ["/app/nestwatch"]