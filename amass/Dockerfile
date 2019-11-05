FROM alpine:latest as builder

WORKDIR /
RUN apk add --no-cache wget unzip && rm -rf /var/cache/apk/*

RUN wget https://github.com/theblackturtle/github-releases/releases/download/v0.1.1/github-releases_linux_amd64 && chmod +x github-releases_linux_amd64

RUN ./github-releases_linux_amd64 --user OWASP --project Amass --kernel linux --architecture amd64 --download
RUN rm github-releases_linux_amd64
RUN unzip amass_*_linux_amd64.zip && mv amass_*_linux_amd64 amass

FROM alpine:latest
COPY --from=builder /amass/amass /bin/amass
COPY --from=builder /amass/examples/wordlists/ /wordlists/
RUN chmod +x /bin/amass
ENV HOME /
ENTRYPOINT ["/bin/amass"]
