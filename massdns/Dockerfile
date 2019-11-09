FROM alpine:latest

WORKDIR /
RUN apk --update --no-cache add ldns \
  && apk --no-cache --virtual .deps add ldns-dev \
                                        git \
                                        build-base \
  && git clone --branch=master \
               --depth=1 \
               https://github.com/blechschmidt/massdns.git \
  && cd massdns \
  && make \
  && mv bin/massdns /bin/massdns \
  && rm -rf /massdns \
  && apk del .deps

# ENTRYPOINT ["/bin/massdns"]