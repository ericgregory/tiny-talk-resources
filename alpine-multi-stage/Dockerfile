FROM golang:1.21 as build

WORKDIR /go/src/app

COPY . .
RUN go mod download && go mod verify
RUN CGO_ENABLED=0 go build -o /go/bin/app

FROM alpine:3.18

COPY --from=build /go/bin/app /
CMD ["/app"]
EXPOSE 80

