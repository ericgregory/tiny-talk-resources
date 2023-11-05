FROM golang:1.21 as build

WORKDIR /go/src/app

COPY . .
RUN go mod download && go mod verify
RUN CGO_ENABLED=0 go build -o /go/bin/app

FROM scratch

COPY --from=build /go/bin/app /
# Scratch-built images will be missing certs, users, and timezones. Lines to include these might look like...
# COPY --from=build /etc/ssl/certs/ca-certificates.crt /etc/ssl/certs/
# COPY --from=build /etc/passwd /etc/passwd
# COPY --from=build /usr/share/zoneinfo /usr/share/zoneinfo
CMD ["/app"]
EXPOSE 80

