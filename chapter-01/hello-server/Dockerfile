FROM golang:1.21 AS builder
WORKDIR /app
COPY . .
ENV CGO_ENABLED=0
RUN go build -o main.go -o hello .

FROM scratch
COPY --from=builder /app/hello /hello
ENTRYPOINT [ "/hello" ]