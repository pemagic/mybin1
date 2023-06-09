FROM golang:alpine AS builder
WORKDIR /app
COPY . .
RUN go build -ldflags="-s -w" -tags netgo -trimpath -o mybin1 main.go

FROM alpine
WORKDIR /app
COPY --from=builder /app/mybin1 .

EXPOSE 8080
CMD ["/app/mybin1"]