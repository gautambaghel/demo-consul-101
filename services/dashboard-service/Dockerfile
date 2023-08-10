FROM golang:1.19 as builder

WORKDIR /app

COPY . .

# Build
RUN GOOS=linux GOARCH=amd64 go build -a -o dashboard-service

FROM alpine:latest

WORKDIR /app

# install binary
COPY --from=builder /app/dashboard-service .

EXPOSE 9002
ENV PORT 9002
ENV COUNTING_SERVICE_URL http://counting.service.consul:9001

CMD ["./dashboard-service"]
