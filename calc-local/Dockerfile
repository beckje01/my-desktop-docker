FROM golang:stretch as builder
RUN go get github.com/alfredxing/calc/...


FROM alpine:latest
COPY --from=builder /go/bin/calc .
ENTRYPOINT ["calc"]