FROM golang:1.23-alpine

WORKDIR /app

# Install essential build tools
RUN apk add --no-cache gcc musl-dev

# Install air for hot reload
RUN go install github.com/air-verse/air@latest

COPY go.mod go.sum ./
RUN go mod download

COPY . .

EXPOSE 8080

# Use air for development
CMD ["air"]