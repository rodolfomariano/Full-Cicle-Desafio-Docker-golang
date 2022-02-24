FROM golang:alpine as builder

WORKDIR /app 
COPY . . 
RUN go mod init app 
RUN CGO_ENABLED=0 GOOS=linux go build main.go

FROM scratch 

COPY --from=builder /app . 

ENTRYPOINT ["./main"]


