FROM alpine:latest

RUN apk add --no-cache \
    ca-certificates \
    libpcap-dev

RUN set -x \
	&& apk add --no-cache --virtual .build-deps \
		build-base \
		clang \
		clang-dev \
		git \
		linux-headers \
	&& rm -rf /var/lib/apt/lists/* \
	&& git clone  https://github.com/robertdavidgraham/masscan.git /usr/src/masscan \
	&& ( \
	cd /usr/src/masscan \
	&& make \
	&& make install \
	) \
	&& rm -rf /usr/src/masscan \
	&& apk del .build-deps


CMD ["masscan"]
