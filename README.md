# Library Management System

A full-stack MERN project that manages books in a library, providing two types of users: Admin and Customer. Admins can add, update, and remove books, while customers can view the available books and borrow them.

## Features

- **Admin:**
  - Add new books
  - Update existing books
  - Remove books
  - Manage borrowers (Issue and return books)

- **Customer:**
  - View the list of books
  - Check if books are available
  - Borrow books
  - Return borrowed books
  - View borrowed books with rent calculation based on borrowing duration

## Technology Stack

- **Frontend:** React, Bootstrap
- **Backend:** Node.js, Express.js
- **Database:** MongoDB with Mongoose
- **Authentication:** JWT (JSON Web Tokens) for token-based authentication
- **Password Encryption:** bcryptjs for hashing passwords
- **Cross-Origin Resource Sharing (CORS):** Enabled for handling cross-origin requests

## Project Structure

```
/Library-Management-System
├── /frontend           # Frontend React app
│   ├── /src
│   ├── /public
│   └── ...
├── /backend            # Backend Node.js app
│   ├── /configs        # Configuration files (auth.config.js, db.config.js, server.config.js)
│   ├── /controllers    # API endpoint logic
│   ├── /models         # Mongoose models
│   ├── /routes         # API routes
│   └── ...
└── README.md           # This README file
```

## API Endpoints

### User Authentication
- **Register:** `POST /LMS/api/v1/users/signup`
- **Login:** `POST /LMS/api/v1/users/login`

### Book Management (Admin only)
- **Add Book:** `POST /LMS/api/v1/books/add`
- **Update Book:** `POST /LMS/api/v1/books/update`
- **Remove Book:** `POST /LMS/api/v1/books/remove`
- **Issue Book (Borrow):** `POST /LMS/api/v1/books/borrow`
- **Return Book:** `POST /LMS/api/v1/books/return`

### Book Viewing and Borrowing (Customer)
- **View Books:** Customers can see available books via the frontend interface.
- **Borrow Book:** Customers can borrow available books.
- **Return Book:** Customers can return borrowed books, and the system will calculate rent based on the borrowing period.
- **View Borrowed Books:** Customers can view their borrowed books along with rent details.

## Setup and Installation

### Backend
1. Clone the repository and navigate to the backend folder:
   ```bash
   git clone https://github.com/pranabdwibedi/Library-Management-System.git
   cd Library-Management-System/backend
   ```
2. Install dependencies:
   ```bash
   npm install
   ```
3. Set up environment variables by creating `auth.config.js, db.config.js, server.config.js` in a `configs` folder in the `backend` directory:
   - In `auth.config.js`:
     ```js
     SECRET = <Your secret for jwt token>
     ADMIN_SECRET = <Secret code for admin creation>
     ```
   - In `db.config.js`:
     ```js
     URI = <your_mongodb_connection_string>
     ```
   - In `server.config.js`:
     ```js
     PORT=<your_port>
     ```
4. Start the backend server:
   ```bash
   npm start
   ```

### Frontend
1. Navigate to the frontend folder:
   ```bash
   cd ../frontend
   ```
2. Install dependencies:
   ```bash
   npm install
   ```
3. Start the frontend development server:
   ```bash
   npm start
   ```

### Configuration Files
- **auth.config.js:** Contains JWT secret and token-related configurations.
- **db.config.js:** Manages MongoDB connection settings.
- **server.config.js:** Includes server settings such as port number and CORS setup.

## Usage

1. **Admin:**
   - Use the signup and login API endpoints to register and log in as an admin.
   - Add, update, remove, and manage books via the respective API endpoints.
   - Issue (borrow) and return books for customers.

2. **Customer:**
   - View available books, borrow books, return books, and view your borrowed books through the frontend interface.

## Libraries and Dependencies

- **Backend:**
  - Express.js
  - Mongoose
  - bcryptjs
  - jwt (jsonwebtoken)
  - cors
- **Frontend:**
  - React
  - Bootstrap
  - axios
  - jwt-decode

## License

This project is licensed under the MIT License.
