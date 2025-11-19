# API Rate Limiting Service

This project demonstrates the implementation of three popular rate-limiting techniques using Go. It provides a simple REST API endpoint that allows testing and comparing different rate-limiting strategies.

## Features

- Implements Token Bucket rate limiting
- Supports per-client request limiting
- Integrates Tollbooth middleware for production-grade rate control
- Dockerized for easy deployment and portability
- Tested locally and deployed on AWS EC2

## Technologies Used

- Go
- Docker
- AWS EC2
- Tollbooth middleware

## Running the Application Locally

### Start the server

```
go run main.go
```

### Test the endpoint

```
curl -i http://localhost:8080/ping
```

### Make multiple requests

```
for i in {1..6}; do curl http://localhost:8080/ping; done
```

## Docker Setup

### Build the Docker image

```
docker build -t rate-limiter .
```

### Run the container

```
docker run -p 8080:8080 rate-limiter
```

After running the container, test the API:

```
curl -i http://localhost:8080/ping
```

## Deployment

The Dockerized service can be deployed on an AWS EC2 instance.  
Once Docker is installed on the instance, transfer the project or pull the image, build it, and run it using the same commands listed above.
