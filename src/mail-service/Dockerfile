FROM golang:1.18-alpine as builder

LABEL stage=go-builder

RUN mkdir /app

COPY . /app

WORKDIR /app

RUN CGO_ENABLED=0 go build -o mailerApp ./cmd/api

RUN chmod +x /app/mailerApp

FROM alpine:latest

LABEL stage=go-deploy

RUN mkdir /app

COPY --from=builder /app /app

CMD [ "/app/mailerApp" ]