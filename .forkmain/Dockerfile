##
## Build
##
FROM golang:1.18-buster AS builder

WORKDIR /workdir

COPY ./ ./

RUN go build -o app tidb-server/main.go

##
## Run
##
FROM golang:1.18-buster

WORKDIR /workdir

COPY --from=builder /workdir/ ./

EXPOSE 4000

CMD ["sh", "-c", "./app"]
