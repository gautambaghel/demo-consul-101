FROM golang:1.19

WORKDIR /app

COPY . .

EXPOSE 9002
ENV PORT 9002
ENV COUNTING_SERVICE_URL http://counting.service.consul:9001

RUN go get
CMD ["go" "run" "main.go"]
