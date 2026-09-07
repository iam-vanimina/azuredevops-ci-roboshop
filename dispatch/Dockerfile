# ---------- Build stage ----------
FROM golang:1.17  

WORKDIR /app

COPY *.go .
#COPY go.mod go.sum ./

RUN go mod init dispatch && go get
RUN go mod download

RUN go build -o /app/dispatch .
RUN chmod +x /app/dispatch
EXPOSE 8080
RUN addgroup -S roboshop && adduser -S roboshop -G roboshop
CMD ["/app/dispatch"]
