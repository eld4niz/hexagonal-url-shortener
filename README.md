# URL Shortener with Hexagonal Architecture in Go
A powerful URL shortener built with Golang, MongoDB, and Redis using the hexagonal architecture pattern.

# Overview
This project is a URL shortener implemented in Go, following the hexagonal architecture pattern. It uses either MongoDB or Redis as the database to store short codes, and supports both msgpack and JSON as data types.

# Features
- Shorten long URLs into unique short codes
- Retrieve original URLs using short codes
- Supports both MongoDB and Redis as backend storage
- Allows for serialization using both msgpack and JSON

# Dependencies
- Go (>=1.16)
- MongoDB (if using MongoDB as backend)
- Redis (if using Redis as backend)

# Serialization
This project supports two serialization formats:

- Msgpack: Used for efficient binary encoding.
- JSON: Human-readable and widely supported.

To specify the serialization format, include the appropriate Content-Type header in your request:

- Msgpack: Content-Type: application/msgpack
- JSON: Content-Type: application/json


# API Endpoints
POST - /
- Request Body: 
```json 
{"url": "http://www.google.com"}
```

- Response Body:
```json

{
    "code": "zmOk1l4Ig",
    "url": "https://www.google.com/",
    "created_at": 1699457303
}

```

GET - /{short_code}
- Retrieve the original URL associated with a short code
