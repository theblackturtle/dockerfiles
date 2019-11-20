FROM alpine:latest

RUN apk --no-cache add unbound libressl

EXPOSE 53 53/udp
ENTRYPOINT ["unbound", "-d", "-p"]
