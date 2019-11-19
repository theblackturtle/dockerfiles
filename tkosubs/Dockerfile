FROM golang:1.13-alpine3.10 as builder

RUN apk --no-cache add git
RUN go get github.com/anshumanbh/tko-subs; exit 0
WORKDIR /go/src/github.com/anshumanbh/tko-subs
RUN go install ./...

FROM alpine:latest
RUN apk --no-cache add ca-certificates
COPY --from=builder /go/bin/tko-subs /bin/tko-subs
COPY --from=builder /go/src/github.com/anshumanbh/tko-subs/providers-data.csv /providers-data.csv

CMD ["/bin/tko-subs"]