FROM golang:1.13.4-alpine3.10 AS builder

RUN apk --no-cache add git
RUN go get github.com/tomnomnom/assetfinder; exit 0
WORKDIR /go/src/github.com/tomnomnom/assetfinder
RUN go install ./...

FROM alpine:latest
RUN apk --no-cache add ca-certificates
COPY --from=builder /go/bin/assetfinder /bin/assetfinder
ENV HOME /

CMD ["assetfinder"]