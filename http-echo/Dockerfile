FROM golang:latest

EXPOSE 8000/tcp

# Set destination for COPY
WORKDIR /app

COPY go.mod .
RUN go mod download

# Copy the source code.
COPY . ./

# Build
RUN go build -o /http-echo .

# Run
ENTRYPOINT [ "/http-echo" ]
