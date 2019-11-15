FROM golang:1.13-alpine3.10 as builder
RUN apk --no-cache add git
RUN go get github.com/michenriksen/aquatone; exit 0
WORKDIR /go/src/github.com/michenriksen/aquatone
RUN go install ./...

FROM zenika/alpine-chrome:latest
COPY --from=builder /go/bin/aquatone /bin/aquatone