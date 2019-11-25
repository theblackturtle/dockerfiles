FROM golang:1.13-alpine3.10 as builder

RUN apk --no-cache add git
RUN go get github.com/tomnomnom/waybackurls; exit 0
WORKDIR /go/src/github.com/tomnomnom/waybackurls
RUN go install ./...

FROM alpine:latest
RUN apk --no-cache add ca-certificates
COPY --from=builder /go/bin/waybackurls /bin/waybackurls

CMD ["waybackurls"]