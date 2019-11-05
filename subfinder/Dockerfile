FROM golang:1.13.4-alpine3.10 AS builder

RUN apk --no-cache add git
RUN go get github.com/subfinder/subfinder; exit 0
WORKDIR /go/src/github.com/subfinder/subfinder
RUN go install ./...

FROM alpine:latest
RUN apk --no-cache add ca-certificates
COPY --from=builder /go/bin/subfinder /bin/subfinder
ENV HOME /
ENTRYPOINT ["subfinder"]