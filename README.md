# Serve It - HTTP Server implemented in Go
This is a backend project that serves as the foundation for a social media platform API. It supports user authentication, password hashing, and JWT-based token management (access and refresh tokens) for secure communication. This project uses Go and demonstrates concepts such as middleware, database migrations, and clean architecture.

## Features

- User authentication with secure password hashing.
- JWT-based token authentication (access and refresh tokens).
- RESTful API for managing chirps.
- Input sanitization and validation.
- Modular code structure for easy maintainability.

## EndPoints

- "GET /api/healthz" - Tells if the server is up and running , return code 200
- "GET /admin/metrics" - Tells the number of requests or the number of hits 
- "POST /admin/reset" - Reset the count of number of hits and database to intial state
- "POST /api/users" - Used to create the user, taken in email and password
- "PUT /api/users" - Used to update the email and password of the user
- "POST /api/chirps" - Used to create chirp(like a tweet) 
- "GET /api/chirps" - Used to get all the chirps of the user
- "GET /api/chirps/{chirpID}" - Used to get a chirp by chirp id of the user
- "POST /api/login" - Used to login the user and generates the JWT and refresh token.
- "POST /api/refresh" - Refresh the JWT Token
- "POST /api/revoke" - Used to revoke the refresh token
- "DELETE /api/chirps/{chirpID}" - Delete the chirp by id 
- "POST /api/polka/webhooks" - Used to handle the weebhook 

## Prerequisites

Ensure you have the following installed:

- [Go](https://golang.org/dl/) (1.20+ recommended)
- [PostgreSQL](https://www.postgresql.org/)
- [Gose](https://github.com/pressly/goose) for database migrations

## Installation

1. Clone the repository:
   ```bash
   git clone https://github.com/your-username/chirpy.git

2.  ```bash
    cd chirpy

3.  Install the dependencies
    ```bash
    go mod tidy

4.  Configure environment variables
    ```bash
    DB_URL=postgres://username:password@localhost:5432/chirpy?sslmode=disable
    JWT_SECRET=your_secret_key

5.  Run the migrations
    ```bash
    goose postgres <DB_URL> up

6.  Start the Server
    ```bash
    go build -o out && ./out

## Contact

Author : Aakash Chauhan
