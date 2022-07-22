FROM golang:1.16-alpine

EXPOSE 8000/tcp
# Set destination for COPY
WORKDIR /app

COPY go.mod .
RUN go mod download

# Copy the source code. Note the slash at the end, as explained in
# https://docs.docker.com/engine/reference/builder/#copy
COPY . ./

# Build
RUN go build -o /http-echo .

# This is for documentation purposes only.
# To actually open the port, runtime parameters
# must be supplied to the docker command.


# (Optional) environment variable that our dockerised
# application can make use of. The value of environment
# variables can also be set via parameters supplied
# to the docker command on the command line.
#ENV HTTP_PORT=8081

# Run
ENTRYPOINT [ "/http-echo" ]

