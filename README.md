# Auth Backend

The **Auth Backend** is a Node.js-based authentication and user management system. It provides secure user registration, login, and note management functionality. This backend is designed to work seamlessly with a frontend application, such as a login form or dashboard.

## Features

- **User Registration**: Allows new users to register with a username, email, and password.
- **User Login**: Authenticates users and provides a JWT token for secure access.
- **JWT Authentication**: Protects routes and ensures secure communication.
- **Note Management**: Users can save and update personal notes.
- **MongoDB Integration**: Stores user data and notes in a MongoDB database.

## Getting Started

Follow these steps to set up and run the backend server on your local machine.

### Prerequisites

Ensure you have the following installed:

- [Node.js](https://nodejs.org/) (v14 or higher)
- [npm](https://www.npmjs.com/) or [yarn](https://yarnpkg.com/)
- [MongoDB](https://www.mongodb.com/) (local or cloud instance)

### Installation

1. Clone the repository:
    ```bash
    git clone https://github.com/your-username/auth-backend.git
    ```
2. Navigate to the project directory:
    ```bash
    cd auth-backend
    ```
3. Install dependencies:
    ```bash
    npm install
    ```

### Configuration

1. Create a `.env` file in the root directory and add the following:
    ```
    MONGO_URI=your-mongodb-connection-string
    JWT_SECRET=your-jwt-secret
    ```
   Replace `your-mongodb-connection-string` with your MongoDB URI and `your-jwt-secret` with a secure secret key for JWT.

### Running the Server

1. Start the server:
    ```bash
    npm start
    ```
2. The server will run on:
    ```
    http://localhost:5000
    ```

## API Endpoints

### Authentication

- **POST /api/auth/register**  
  Registers a new user.  
  **Request Body**:  
  ```json
  {
    "username": "exampleUser",
    "email": "example@example.com",
    "password": "securePassword"
  }
  ```

- **POST /api/auth/login**  
  Logs in an existing user and returns a JWT token.  
  **Request Body**:  
  ```json
  {
    "username": "exampleUser",
    "password": "securePassword"
  }
  ```

### Protected Routes (Require JWT)

- **POST /api/auth/notes**  
  Updates the user's notes.  
  **Request Body**:  
  ```json
  {
    "userNotes": ["Note 1", "Note 2"]
  }
  ```

- **GET /api/auth/auth**  
  Verifies the user's authentication and returns user details.

## Project Structure

- **index.js**: Entry point of the application.
- **models/user.js**: Defines the MongoDB schema for user data.
- **routes/authRoutes.js**: Contains authentication and note management routes.
- **.env**: Configuration file for environment variables.

## Dependencies

- **express**: Web framework for Node.js.
- **mongoose**: MongoDB object modeling for Node.js.
- **bcryptjs**: Library for hashing passwords.
- **jsonwebtoken**: Library for generating and verifying JWT tokens.
- **dotenv**: Loads environment variables from a `.env` file.
- **cors**: Middleware for enabling Cross-Origin Resource Sharing.

## Contributing

We welcome contributions! Here's how you can help:

1. Fork the repository.
2. Create a new branch for your feature or bug fix:
    ```bash
    git checkout -b feature-name
    ```
3. Commit your changes and push the branch:
    ```bash
    git push origin feature-name
    ```
4. Submit a pull request.

## License

This project is licensed under the [MIT License](LICENSE). Feel free to use it as you like!

---
Happy coding! 🚀