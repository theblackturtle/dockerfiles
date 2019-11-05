FROM alpine:latest

RUN apk add --no-cache wget unzip && rm -rf /var/cache/apk/*

RUN wget https://github.com/theblackturtle/github-releases/releases/download/v0.1.1/github-releases_linux_amd64 && chmod +x github-releases_linux_amd64

RUN ./github-releases_linux_amd64 --user OWASP --project Amass --kernel linux --architecture amd64 --download
RUN rm github-releases_linux_amd64
RUN unzip amass_*_linux_amd64.zip && mv amass_*_linux_amd64 amass && chmod +x amass/amass

WORKDIR amass
ENTRYPOINT ["./amass"]
