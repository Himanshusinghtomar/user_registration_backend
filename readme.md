# User Registration Backend

This is a Node.js-based backend application for user registration, built with MongoDB (cloud) for the database and password hashing for secure storage. The application follows best practices for authentication and data security.

## Features

- User registration with secure password hashing.
- MongoDB cloud integration using Mongoose.
- Input validation using `express-validator`.
- Environment variable support using `dotenv`.
- RESTful API structure.

---

## Prerequisites

Ensure you have the following installed:

- [Node.js](https://nodejs.org/) (v14 or higher recommended)
- [MongoDB Atlas](https://www.mongodb.com/cloud/atlas) account
- A package manager (npm or yarn)

---

## Getting Started

### 1. Clone the Repository

```bash
git clone https://github.com/your-repo/user_registration_backend.git
cd user_registration_backend
```

### 2. Install Dependencies

```bash
npm install
```

### 3. Set Up Environment Variables

Create a `.env` file in the root of your project and add the following:

```env
PORT=3000
MONGO_URI=<your-mongodb-cloud-connection-string>
JWT_SECRET=<your-secret-key>
```

Replace `<your-mongodb-cloud-connection-string>` with the connection string from MongoDB Atlas and `<your-secret-key>` with a secret string for JWT token generation.

### 4. Run the Application

Start the server:

```bash
npm start
```

The server will start at `http://localhost:3000`.

---

## API Endpoints

### 1. User Registration

**Endpoint:** `/api/register`

**Method:** `POST`

**Request Body:**

```json
{
  "name": "John Doe",
  "email": "johndoe@example.com",
  "password": "securepassword"
}
```

**Response:**

```json
{
  "message": "User registered successfully",
  "user": {
    "id": "unique-user-id",
    "name": "John Doe",
    "email": "johndoe@example.com"
  }
}
```

---

## Folder Structure

```
user_registration_backend/
├── controllers/
│   └── authController.js   # Handles authentication logic
├── models/
│   └── User.js             # User schema and model
├── routes/
│   └── authRoutes.js       # Routes for authentication
├── middlewares/
│   └── validateInput.js    # Input validation middleware
├── .env                    # Environment variables
├── server.js               # Entry point of the application
├── package.json            # Node.js dependencies and scripts
└── README.md               # Project documentation
```

---

## Dependencies

- `express` - Web framework for Node.js
- `mongoose` - MongoDB object modeling tool
- `bcrypt` - Library for hashing passwords
- `dotenv` - Environment variable management
- `express-validator` - Middleware for validating request inputs

---

## Security Considerations

- Passwords are hashed using `bcrypt` before being stored in the database.
- Sensitive information (e.g., database credentials) is stored in environment variables.

---

## Contributing

Contributions are welcome! Please fork this repository and submit a pull request with your changes.

---

## License

This project is licensed under the MIT License. See the `LICENSE` file for details.
