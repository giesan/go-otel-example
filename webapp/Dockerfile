# Stage 1: Build stage
FROM golang:latest AS build

# Set the working directory
WORKDIR /app

# Copy and download dependencies
COPY go.mod go.sum ./
RUN go mod download

# Copy the source code
COPY . .

# Build the Go application
RUN CGO_ENABLED=0 GOOS=linux go build -o go-otel-example .

# Stage 2: Final stage
FROM alpine:edge

# Set the working directory
WORKDIR /app

# Copy the binary from the build stage
COPY --from=build /app/go-otel-example .

# Set the timezone and install CA certificates
RUN apk --no-cache add ca-certificates tzdata

EXPOSE 8080

# Set the entrypoint command
ENTRYPOINT ["/app/go-otel-example"]
