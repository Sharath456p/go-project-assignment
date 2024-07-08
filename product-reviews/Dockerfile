# Use the official Go image as the base
FROM golang:1.17-alpine AS builder

# Set working directory
WORKDIR /go/src/app

# Copy your Go code to the working directory
COPY . .


# Build the Go binary 
RUN go build -o /app/main

# Use a slimmer image for the final image
FROM alpine:latest

# Copy the built binary from the builder stage
COPY --from=builder /app/main /app/main

# Set the entrypoint to run your Go binary
ENTRYPOINT ["/app/main"]
