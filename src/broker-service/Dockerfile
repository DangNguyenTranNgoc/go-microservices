FROM golang:1.18-alpine as builder

LABEL stage=go-builder

RUN mkdir /app

COPY . /app

WORKDIR /app

RUN go install google.golang.org/protobuf/cmd/protoc-gen-go@latest \
&& go install google.golang.org/grpc/cmd/protoc-gen-go-grpc@latest

RUN apk update && apk add protoc

RUN cd /app && protoc --go_out=. --go_opt=paths=source_relative \
                    --go-grpc_out=. --go-grpc_opt=paths=source_relative \
                    logs/logs.proto

RUN CGO_ENABLED=0 go build -o brokerApp ./cmd/api

RUN chmod +x /app/brokerApp

FROM alpine:latest

LABEL stage=go-deploy

RUN mkdir /app

COPY --from=builder /app/brokerApp /app

CMD [ "/app/brokerApp" ]