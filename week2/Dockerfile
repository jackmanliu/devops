FROM golang:1.17 as buildup
COPY ./test.go /app/
WORKDIR /app/
ENV CGO_ENABLED=0
ENV GO111MODULE=on
RUN go build test.go

FROM alpine:3.18.3
COPY --from=buildup /app /app
ENTRYPOINT ["/app/test"]