FROM alpine:latest

RUN apk --no-cache add unbound libressl

COPY ./unbound/unbound.conf /etc/unbound/unbound.conf
RUN unbound-checkconf

ENTRYPOINT ["unbound","-d"]
