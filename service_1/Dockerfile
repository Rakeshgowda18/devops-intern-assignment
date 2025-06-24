FROM golang:1.20-alpine

WORKDIR /app
COPY . .
RUN go build -o service1

EXPOSE 8001
CMD ["./service1"]
