# In-Memory Authentication API

This is a lightweight authentication API built using Node.js and Express. It supports user sign-up, sign-in, and profile retrieval with an in-memory storage approach.

## Features
- **Sign Up**: Register new users.
- **Sign In**: Authenticate existing users and receive a JWT token.
- **Profile Management**: Fetch user information using a valid token.
- **In-Memory Storage**: No database required; all data is stored in-memory for simplicity.

## Live Demo
- **API Base URL**: [https://tridibs-in-memory-authentication-api.onrender.com](https://tridibs-in-memory-authentication-api.onrender.com)

## Frontend
- **Live Application**: [https://tridibs-in-memory-authentication.netlify.app](https://tridibs-in-memory-authentication.netlify.app)
- **Frontend Repository**: [GitHub Repo](https://github.com/Tridib11/Authentcation-UI)

## Installation

1. Clone the repository:
   ```bash
   git clone https://github.com/Tridib11/Authentication-api.git
   ```

2. Navigate to the project folder:
   ```bash
   cd Authentication-api
   ```

3. Install dependencies:
   ```bash
   npm install
   ```

4. Start the server:
   ```bash
   node index.js
   ```
   The server will run on `http://localhost:3000`.

## API Endpoints

### 1. **`GET /`**
- **Description**: Check if the server is running.
- **Response**: 
  ```json
  {
    "msg": "Server is running"
  }
  ```

### 2. **`POST /signup`**
- **Description**: Register a new user.
- **Request Body**:
  ```json
  {
    "username": "your_username",
    "password": "your_password"
  }
  ```
- **Response**:
  ```json
  {
    "msg": "You are signed in successfully"
  }
  ```
- **Error**: 
  ```json
  {
    "msg": "User already exists"
  }
  ```

### 3. **`POST /signin`**
- **Description**: Log in a user and receive a JWT token.
- **Request Body**:
  ```json
  {
    "username": "your_username",
    "password": "your_password"
  }
  ```
- **Response**:
  ```json
  {
    "token": "your_jwt_token"
  }
  ```
- **Error**:
  ```json
  {
    "msg": "Sorry user does not exist!"
  }
  ```

### 4. **`GET /me`**
- **Description**: Fetch user information. Requires a valid JWT token.
- **Headers**:
  ```json
  {
    "token": "your_jwt_token"
  }
  ```
- **Response**:
  ```json
  {
    "username": "your_username",
    "password": "your_password"
  }
  ```
- **Error**:
  ```json
  {
    "msg": "User not found"
  }
  ```

### Middleware

- **`auth`**: Verifies the JWT token.
- **`logger`**: Logs the incoming request method.

## Tech Stack
- **Backend**: Node.js, Express
- **Authentication**: JWT (JSON Web Tokens)
- **CORS**: Enabled for cross-origin requests
- **Frontend**: Deployed on Netlify

## How It Works
1. **Sign Up** to create a new account.
2. **Sign In** to receive a JWT token.
3. Use the token to access the **Profile Information** endpoint.

## Project Structure
```bash
.
├── index.js         # Main server file
├── package.json     # Project dependencies
└── README.md        # Documentation
```

## License
This project is licensed under the MIT License. Feel free to use and modify it as needed.

## Author
**Tridib**  
[GitHub](https://github.com/Tridib11)