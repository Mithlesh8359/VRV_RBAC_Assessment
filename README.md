# VRV Role-Based Access Control (RBAC) System

## Overview
The **VRV Role-Based Access Control (RBAC) System** is a secure implementation designed to manage **Authentication**, **Authorization**, and access control using roles. It provides functionality for user registration, login, logout, and route access restriction based on roles such as **Admin**, **User**, and **Moderator**. This system ensures that users have the least privileges necessary for their tasks, enhancing security.

The project utilizes modern authentication methods, including **JWT (JSON Web Tokens)** for token-based authentication and middleware for role enforcement.

---

## Key Features
### User Authentication
- **Registration and Login**: Secure user registration with unique email and password. Authenticated users are issued a JWT token.
- **Password Hashing**: Ensures password security using `bcrypt`.

### Role Management
- Predefined roles such as **Admin**, **User**, and **Moderator** with specific permissions.
- Easy scalability to introduce new roles and permissions.

### Role-Based Middleware
- Middleware to verify tokens and enforce role-based access control (RBAC).
- Unauthorized access attempts result in meaningful error messages.

### Session Management
- JWT tokens have configurable expiration.
- Users can log out, invalidating their sessions.

---

## Technologies Used
- **Backend**: Node.js, Express.js
- **Database**: MongoDB (Mongoose)
- **Authentication**: JSON Web Tokens (JWT) and bcrypt for password hashing
- **Tools**: Postman for API testing

---

## My Contribution
### System Design
- Designed a scalable **database schema** to manage roles and permissions efficiently.
- Organized the project structure for maintainability and scalability.

### Authentication
- Implemented secure registration and login functionality with hashed passwords using `bcrypt`.
- Integrated **JWT** for session management.

### Authorization
- Created middleware to validate JWT tokens and decode user roles.
- Enforced role-based access control for protected routes.

### API Development
- Developed endpoints for user registration, login, logout, and role-restricted routes.
- Added role-specific routes like an **Admin Dashboard**.

### Security Enhancements
- Applied input validation and token expiration for secure interactions.
- Used environment variables to secure sensitive data.

### Testing
- Conducted manual testing using Postman to verify endpoints.
- Tested edge cases like invalid tokens, expired tokens, and unauthorized access attempts.

---

## Instructions to Set Up and Test
### Setup
- 1.Clone the repository to your local machine:
   ```bash
   git clone https://github.com/Mithlesh8359/VRV_RBAC_Assessment
   cd VRV_RBAC_Assessment
- 2.Install dependencies
  ```bash
   npm install
- 3.Configure environment variables in a .env file:
  ```bash
  PORT=5000
  MONGO_URI=your_mongo_database_url
  JWT_SECRET=your_secret_key
  JWT_EXPIRE=1d
- 4.Start the development server:
  ```bash
  npm start
## Testing the System
  - Use Postman or similar tools to test the following endpoints:
  - Register: POST /api/auth/register
  - Login: POST /api/auth/login
  - Get Profile: GET /api/users/profile (requires JWT token)
  - Admin Route: GET /api/users/admin (requires Admin role)
  - Test edge cases:
  - Attempt login with incorrect credentials.
  - Access protected routes without a token or with an expired/invalid token.
  - Try accessing Admin routes as a non-admin user.
