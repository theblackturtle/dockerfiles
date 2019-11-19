FROM golang:1.13-alpine3.10 as builder

RUN apk --no-cache add git
RUN go get github.com/haccer/subjack; exit 0
WORKDIR /go/src/github.com/haccer/subjack
RUN go install ./...

FROM alpine:latest
RUN apk --no-cache add ca-certificates
COPY --from=builder /go/bin/subjack /bin/subjack
COPY --from=builder /go/src/github.com/haccer/subjack/fingerprints.json /src/github.com/haccer/subjack/fingerprints.json

CMD ["/bin/subjack"]