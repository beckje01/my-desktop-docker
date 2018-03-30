FROM golang:stretch as builder
RUN go get github.com/fullscreen/aws-rotate-key/...

FROM alpine:latest
COPY --from=builder /go/bin/aws-rotate-key .
ENTRYPOINT ["./aws-rotate-key"]