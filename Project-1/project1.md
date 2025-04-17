## Containerize an Express App
Express JS + docker
Here's a `README.md` file for your project that gives a brief overview and highlights the use of Docker:

---

```markdown
# Simple Express User Registration API

This is a lightweight Node.js Express application that provides basic user registration and retrieval functionalities via a RESTful API. It demonstrates how to handle simple HTTP GET and POST requests, store in-memory user data, and respond with appropriate messages.

### Features

- `GET /` – Returns a "Hello world!" message.
- `GET /users` – Retrieves the list of registered users.
- `POST /users` – Registers a new user by accepting a `userId` in the request body.

### Tech Stack

- Node.js
-Express
- Docker (for containerization)

## Getting Started

### 1. Clone the Repository

```bash
git clone https://github.com/your-username/your-repo-name.git
cd your-repo-name
```

### 2. Build and Run with Docker

Make sure Docker is installed on your system.

```bash
# Build the Docker image
docker build -t express-user-api .

# Run the container
docker run -p 3000:3000 express-user-api
```

### 3. API Endpoints

- `GET http://localhost:3000/` – Hello World
- `GET http://localhost:3000/users` – Get all users
- `POST http://localhost:3000/users` – Register a new user  
  Body: 
  ```json
  {
    "userId": "your-unique-id"
  }
  ```

## Notes

- This app stores data in-memory; restarting the server will reset all user data.
- Intended for learning and demonstration purposes.

---
## Thanks to the Educator Lauro muller for explaining this project 🤩️. 
