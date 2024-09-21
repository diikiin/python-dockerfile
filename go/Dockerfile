FROM golang:1.23.1 AS compiler
LABEL authors="dikin"

WORKDIR /app
COPY . .

RUN go build -o app .

FROM alpine:latest

WORKDIR /app
COPY --from=compiler /app/app .

CMD ["./app"]