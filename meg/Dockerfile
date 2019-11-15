FROM golang:1.13.4-alpine3.10 AS builder

RUN apk --no-cache add git
RUN go get github.com/tomnomnom/meg; exit 0
WORKDIR /go/src/github.com/tomnomnom/meg
RUN go install ./...

FROM alpine:latest
RUN apk --no-cache add ca-certificates
COPY --from=builder /go/bin/meg /bin/meg

CMD ["meg"]