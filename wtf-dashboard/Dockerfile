FROM golang:alpine as builder
RUN apk --no-cache add git
RUN go get github.com/senorprogrammer/wtf/...

FROM alpine:latest
RUN apk --no-cache add ca-certificates
RUN apk --no-cache add tzdata
WORKDIR /root/
COPY --from=builder /go/bin/wtf .
ENTRYPOINT ["./wtf"]
