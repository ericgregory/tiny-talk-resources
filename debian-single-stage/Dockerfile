FROM golang:1.21

WORKDIR /usr/src/app

# In a real-world application that actually has dependencies, you’d want to copy the go.sum file in the line below, either by copying everything or like so: COPY go.mod go.sum ./
COPY go.mod ./
RUN go mod download && go mod verify

COPY . .
RUN go build -v -o /usr/local/bin/app ./...

CMD ["app"]





