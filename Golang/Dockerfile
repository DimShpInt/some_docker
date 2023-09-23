FROM golang:1.20.5-alpine as buildcode
WORKDIR /app
COPY go.mod go.sum ./
RUN go mod download
COPY . .
RUN go build -o myhomework
FROM scratch
COPY --from=buildcode /app/myhomework /usr/local/bin/myhomework
CMD ["/usr/local/bin/myhomework"]
